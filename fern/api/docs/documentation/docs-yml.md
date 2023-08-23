Every Fern Docs web site has a special file called `docs.yml`, which includes all the docs-wide configuration.

```yaml
title: Fern | Docs
navigation:
  - section: Home
    contents:
      - page: Introduction
        path: ./intro.md
      - page: Authentication
        path: ./auth.md
      - page: Versioning
        path: ./versioning.md
  - api: API Reference
navbar-links:
  - type: secondary
    text: Contact support
    url: https://example.com/support
  - type: primary
    text: Login
    url: https://example.com/login
colors:
  accentPrimary: "#a6d388"
logo:
  path: ./images/logo.png
  height: 70
  href: https://example.com?utm_source=documentation&utm_medium=logo
favicon: ./images/favicon.png
```

## Title

The <title> tag defines the title of the document. The title must be text-only, and it is shown in the browser's title bar or in the page's tab. The title is required. The contents of a page title is very important for search engine optimization (SEO). [Read more.](https://www.w3schools.com/tags/tag_title.asp)

## Navigation

The navigation organizes your documentation in the nav bar. Each section has a title and a list of contents. Contents contain a page name and a file path. The supported file types are `.md` or `.mdx`.

## API Reference

A key benefit of using Fern Docs is that you get your API Reference with just one line. Add `- api: API Reference` and Fern will take care of the rest! You'll see your endpoints, types, and errors populated from your API definition automatically.

## Navigation Bar

Having easy-to-use navigation is important for any documentation web site. In `navbar-links`, you may specify a list of links.

```
navbar-links:
  - type: secondary
    text: Contact support
    url: https://example.com/support
  - type: primary
    text: Login
    url: https://example.com/login
```

### Link type

A link can be `primary` or `secondary`. Primary links are designed to stand out and indicate that they are clickable with an arrow `>`. You may have one primary link.

### Link text

A link has text which is displayed to the user.

### Link URL

A link has a URL which a user is directed to. By default, URLs open in a new browser tab.

Tip: you may want to use a trackable link for the URLs, such as [UTM parameters](https://en.wikipedia.org/wiki/UTM_parameters).

## Colors

You may specify a primary accent color using the [Hexadecimal color](https://www.w3schools.com/colors/colors_hexadecimal.asp). The primary accent color is used in many places, including:

- to indicate the page a user is on within the navbar
- the background of a primary link button
- to underline hyperlinks
- the next and previous page navigation buttons

```
colors:
  accentPrimary: "#a6d388"
```

## Logo

Defines parameters for the website's logo display.

```
logo:
  path: ./images/logo.png
  height: 70
  href: https://example.com?utm_source=documentation&utm_medium=logo
```

### Path

`path` specifies the image file location. Supported logo file types include `.png` and `.svg`.

### Height

`height` sets the logo's height in pixels.

### Href

`href` provides a hyperlink for the logo, often used to point to the website homepage.

## Favicon

Specifies the path to a favicon image, which is typically displayed in a browser tab or bookmark. This small but crucial customization enhances user experience by allowing the website to have a unique and recognizable icon. Supported file types are `.png` and `.ico`.
