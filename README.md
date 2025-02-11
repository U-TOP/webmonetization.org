*Read this in other languages: [日本語](README-ja.md).*

# WebMonetization.org

[View live site](https://webmonetization.org)

This repo is the home of the proposed Web Monetization standard.

View the [explainer](https://webmonetization.org/docs/explainer.html), or read
the proposed [spec](https://webmonetization.org/specification.html).

## Contribute

This website was created with [Docusaurus](https://docusaurus.io/).

### Local Development

1. Make sure all the dependencies for the website are installed:

```sh
# Install dependencies
$ cd website
$ yarn
```

2. Run your dev server:

```sh
# Start the site
$ yarn start
```

### Directory Structure

Your project file structure should look something like this

```
webmonetization.org
├── docker-compose.yml
├── Dockerfile
├── docs
│   ├── api.md
│   ├── assets
│   │   └── flow.svg
│   ├── explainer.md
│   ├── getting-started.md
│   ├── receiving.md
│   ├── sending.md
│   └── specification.md
├── LICENSE
├── README.md
└── website
    ├── core
    │   └── Footer.js
    ├── i18n
    │   └── en.json
    ├── package.json
    ├── pages
    │   └── en
    │       ├── docs.js
    │       ├── index.js
    │       └── meta-tag.js
    ├── sidebars.json
    ├── siteConfig.js
    ├── static
    │   ├── css
    │   │   └── custom.css
    │   ├── img
    │   │   ├── coil_logo.svg
    │   │   ├── copy_icon.svg
    │   │   ├── favicon.ico
    │   │   ├── fav-webmonetization.png
    │   │   ├── gatehub_logo.svg
    │   │   ├── grey_wm_logo.svg
    │   │   ├── stronghold_logo.svg
    │   │   ├── tipbot_logo.svg
    │   │   ├── webmon_icon_simple.svg
    │   │   ├── webmon_icon.svg
    │   │   ├── wm-icon-animated.svg
    │   │   └── wm-icon.svg
    │   ├── js
    │   │   └── custom.js
    │   └── specification.html
    └── yarn.lock
```

## Editing Content

### Editing an existing docs page

Edit docs by navigating to `docs/` and editing the corresponding document:

`docs/doc-to-be-edited.md`

```markdown
---
id: page-needs-edit
title: This Doc Needs To Be Edited
---

Edit me...
```

For more information about docs, click
[here](https://docusaurus.io/docs/en/navigation)

## Adding Content

### Adding a new docs page to an existing sidebar

1. Create the doc as a new markdown file in `/docs`, example
   `docs/newly-created-doc.md`:

```md
---
id: newly-created-doc
title: This Doc Needs To Be Edited
---

My new content here..
```

1. Refer to that doc's ID in an existing sidebar in `website/sidebar.json`:

```javascript
// Add newly-created-doc to the Getting Started category of docs
{
  "docs": {
    "Getting Started": [
      "quick-start",
      "newly-created-doc" // new doc here
    ],
    ...
  },
  ...
}
```

For more information about adding new docs, click
[here](https://docusaurus.io/docs/en/navigation)

### Adding items to your site's top navigation bar

1. Add links to docs, custom pages or external links by editing the headerLinks
   field of `website/siteConfig.js`:

`website/siteConfig.js`

```javascript
{
  headerLinks: [
    ...
    /* you can add docs */
    { doc: 'my-examples', label: 'Examples' },
    /* you can add custom pages */
    { page: 'help', label: 'Help' },
    /* you can add external links */
    { href: 'https://github.com/facebook/Docusaurus', label: 'GitHub' },
    ...
  ],
  ...
}
```

For more information about the navigation bar, click
[here](https://docusaurus.io/docs/en/navigation)

### Adding custom pages

1. Docusaurus uses React components to build pages. The components are saved as
   .js files in `website/pages/en`:
1. If you want your page to show up in your navigation header, you will need to
   update `website/siteConfig.js` to add to the `headerLinks` element:

`website/siteConfig.js`

```javascript
{
  headerLinks: [
    ...
    { page: 'my-new-custom-page', label: 'My New Custom Page' },
    ...
  ],
  ...
}
```

For more information about custom pages, click
[here](https://docusaurus.io/docs/en/custom-pages).

## Full Documentation

Full documentation can be found on the [website](https://docusaurus.io/).
