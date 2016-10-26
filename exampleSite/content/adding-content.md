---
title: Adding content
---

## Creating pages

Sites are added inside the repo's "content" folder, with each Markdown file within being a new page. For example, this adding-content page is at `content/adding-content.md`.

Each `.md` file should start with a metadata block:
 
```
---
title: Page Title
---
```

Pages aren't automatically added to the left nav. These are configured in the `config.toml` file [as detailed below](#top-level-nav).

## Homepage

The homepage is a special page with the following in the top block within the `.md` file.

```toml
type: index
```

By convention this is in `content/index.md` but any file can be a homepage.

## Top Level Nav

Each top-level nav link is configured in the root folder's `config.toml` file. To add a new link, find the series of `[[menu.main]]` entries.

```toml

[[menu.main]]
	name   = "Adding content"
	url    = "adding-content/"
	weight = 20

```

- The `name` represents the link title.
- The `url` is the page to link to (this should be the filename without `.md`
- The `weight` is the order in the nav which is should appear in. Links with weight `weight = 10` will precede those with `weight = 20`

## In-page Nav

Under the main links are in-page links. These link to places on the current page.

Each time a Markdown `## Second Level Header` is used it will be added automatically.

## Content Formatting

### Paragraph Styles

Paragraphs are simply lines of text. Each double-new-line creates a new paragraph.
Single new lines are not line breaks, but just continue the previous paragraph.

Simple inline content can be \*italic\*, \*\*bold\*\* and \~\~strikethrough\~\~. 

### Headings
 
Headings are added with has characters:

```
## Main headings
```

Main headings are used for the in-page nav

```
### Subheadings
```

### Links and Images

Links can be relative or absolute.

```
[Relative Links](/adding-content) and [Absolute Links](https://www.edmondscommerce.co.uk)
```

[Relative Links](/adding-content) and [Absolute Links](https://www.edmondscommerce.co.uk)

Images are similar:

```
![Alt Text](/images/magento.jpg) and ![Alt Text](https://www.edmondscommerce.co.uk/skin/edmondscommerce-files/images/eclogo.png)
```

![Alt Text](/images/magento.jpg) and ![Alt Text](https://www.edmondscommerce.co.uk/skin/edmondscommerce-files/images/eclogo.png)

Relative images are stored in the `static/images/` folder.

## Code snippets

There are two options:

```
Code can be added `inline`
```

Code can be added `inline`

Or as a block


```
Code can be added as a block
```

## Banner Blocks

### Notes

```go
{{</* note title="Note" */>}}
Nothing to see here, move along.
{{</* /note */>}}
```

This will print the following block:

{{< note title="Note" >}}
Nothing to see here, move along.
{{< /note >}}

### Warnings

```go
{{</* warning title="Don't try this at home" */>}}
Nothing to see here, move along.
{{</* /warning */>}}
```

This will print the following block:

{{< warning title="Don't try this at home" >}}
Nothing to see here, move along.
{{< /warning >}}
