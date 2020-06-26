# Swift Theme

This theme is designed for blogging purposes. Feel free to extend it for other
use cases though.

At its core, it's minimalistic; it doesn't rely on monolithic libraries such e.g
jquery, bootstrap. Instead, it uses *grid css*, *flexbox* & *vanilla js* to
facilitate the `features` outlined below:

![Hugo Swift Theme](https://github.com/onweru/hugo-swift-theme/blob/master/images/screenshot.png)

## Features

* Blog
* Pagination
* Responsive
* Deeplinks
* Dark Mode
* Syntax Highlighting
* [Staticman](#staticman-comments)
  * [reCAPTCHA](https://developers.google.com/recaptcha/docs/display)

## Prerequisites

This theme uses `sass`. Ensure you have the [extended version of hugo](https://github.com/gohugoio/hugo/releases) installed or in your pipeline.

## Installation

Add this theme as a Git submodule inside your Hugo site folder:

```bash
git submodule add https://github.com/onweru/hugo-swift-theme.git themes/hugo-swift-theme
```

## Configuration

You can configure the site using as follows:

1. ### General Information** and **Staticman config

    Use the file `config.toml`.
2. ### menu, footer

    See the **data** files inside the `data/` directory.

    > Follow the `exampleSite/`.
3. Customize Theme colors
    You can do so easily in the [variables sass partial](https://github.com/onweru/hugo-swift-theme/blob/e5af8a1414cd8e1ec5a0817f8e5eb8c8c98e2676/assets/sass/_variables.sass#L13-L21). Use names (e.g red, blue, darkgoldenrod), rgb, rgba, hsla or hex values.
    

## Staticman Comments

By default, [Staticman](https://staticman.net) comments are disabled.
To enable them, you may refer to the
[Staticman config Wiki](https://github.com/onweru/hugo-swift-theme/wiki/staticman-config).

## Written By Block

### How do I include a `written by` ?

  1. Copy [this authors yaml file](https://github.com/onweru/hugo-swift-theme/blob/master/exampleSite/data/authors.yml) from the `exampleSite` to your data directory.

  ```yaml
  - name: "yourName" # if fullName 👇🏻 isn't set, name will be displayed on author card
    fullName: "John Doe" # optional. If set, it will display on author card
    photo: "myAvatar.jpg"
    url: "https://myURLofChoice.domain"
    bio: "It's time to flex. Write a short or not-so-short summary about yourself."
  ```

  2. Specify the name in your content files

  ```yaml
  ...
  author: "yourName" # case sensitive. must match the name value in your saved data 
  ...
  ```
### What if I want to exclude the `written by` from some articles?

Don't include an `author` in your article front matter.

The *authors.yml* file helps you:

  1. Write all your author information in one place. This way, you only specify the author name on your content files (posts). The rest of the data i.e photo, url & bio are automatically pulled from the data file.

  2. In certain situations, you may have different people publishing articles on your blog. For example, you could have someone guest blog. Or may be you have a blog co-author.


## Deeplinks

For all content published using markdown, deeplinks will be added to the pages
so that you can share with precision :smiley: Just   hover on a heading and the
link button will pop. Click it to copy.

## Dark Mode

Today most operating systems & browsers support dark mode. Like twitter, which
automatically turns into dark mode when the user chooses darkmode, this theme
does the same thing.

![Dark Mode](https://github.com/onweru/hugo-swift-theme/blob/master/images/darkmode.jpg)

## Custom Shortcodes

This theme ships with two custom shortcodes (they both use positional parameters):

1. __Video__
    This shortcode can be used to embed a youtube video with custom styling. It takes a solo positional parameter.
    
    ```
    ...
    {{< video "youtubeVideoID" >}}
    ...
    ```

2. __Picture__
    You want to use darkmode images when darkmode is enabled on a device and a regular image on lightmode? It takes 3 positional parameter

    Store these images in the `static/images` directory. 
    
    ```
    ...
    {{< picture "lightModeImage.png" "darkModeImage.png" "Image alt text" >}}
    ...
    ```

## License

The code is available under the
[MIT license](https://github.com/onweru/hugo-swift-theme/blob/master/LICENSE.md).
