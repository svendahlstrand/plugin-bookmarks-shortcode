# 🔖 Bookmarks Shortcode BETA

Share your Micro.blog bookmarks with the world.

![](https://raw.githubusercontent.com/svendahlstrand/plugin-bookmarks-shortcode/main/docs/screenshot.png)

> TODO: Write this.

To get updates on this plug-in, [follow @sod on Micro.blog](https://micro.blog/sod).

## Do you get value from Bookmarks Shortcode? I'd love your support!

Hey! It's me, Sven. Bookmarks Shortcode and my other plug-ins are passion projects released to the world for free. That said, donations are always welcome if you get value from my work.

[💸 Donate $10](https://dahlstrand.net/donate/) or any amount you're comfortable with. Thanks! 🙏

## Bells and whistles

* 🎁 Works out of the box – copy n paste anywhere.
* 🛠 Fully customizable.
* 📋 TODO: Write more!

## Get started

Hello, fellow microblogger! 👋 This plug-in is available as BETA in the official directory. It's easy to install, but be aware that it's early in development. So bugs and weird things will happen. 😅 Thanks for your help with testing.

### Install the plug-in

1. Find [Bookmarks Shortcode in the plug-in directory](https://micro.blog/account/plugins/view/84).
2. Choose the site you want to install the plug-in to.
3. Press *Install*.
4. Congratulations, the plug-in is now installed. On to configuration.

### Configure the plug-in

1. Go to *Plug-ins* and press ⚙️ *Settings* (next to the Bookmarks Shortcode plug-in).

2. Fill in your bookmarks' feed in *JSON Feed URL*. (There's a link to your feed on [this page](https://micro.blog/account/feeds).)

4. Press *Update Settings* and go to the next step.

### Create a page for your bookmarks

Do you have a page already? Skip to step 4.

1. Go to *Pages* and click *New Page*

2. Give it a name (like My Bookmarks).

3. Fill the page with any content you see fit.

4. Add this shortcode where you want your bookmarks to show up: `{{< bookmarks />}}`.

5. Press *Add Page* and pat yourself on the back.

### Make sure it works

1. Go visit your newly created page.

2. Make sure you see the bookmarks as expected.

### Customize the look and feel

The bookmarks list is fully customizable by presenting a template to the `bookmarks` shortcode. Take a look at the default template for inspiration.

#### Default template

This is just for education. You will get the exact same result with `{{< bookmarks />}}`.

```
{{< bookmarks >}}
  {{ range .items }}
    {{ $url := urls.Parse .url }}

    {{ if not .title }}
      <figure>
        <blockquote>
          <p>{{ .content_html | plainify | truncate 140 }}</p>
        </blockquote>
        <figcaption><cite><a class="u-bookmark-of" href="{{ .url }}">{{ $url.Host }}</a></cite></figcaption>
      </figure>
    {{ end }}
  {{ end }}
{{< /bookmarks >}}
```

#### Just a list of URLs

Less is more?

```
{{< bookmarks >}}
  <ul>
    {{ range .items }}
      <li><a class="u-bookmark-of" href="{{ .url }}">{{ .url }}</a></li>
    {{ end }}
  </ul>
{{< /bookmarks >}}
```

### Having troubles?

Feel free to [reach out to @sod on Micro.blog](https://micro.blog/sod) for additional help.
