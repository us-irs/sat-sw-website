IRS Software Website
=======

This website shows the software projects of the satellite division at the Institute of Space
Systems of the University of Stuttgart.

# Development

## Prerequisites

1. Install [hugo](https://gohugo.io/)
2. Install [node](https://nodejs.org/en)

## Building the website

1. Install the npm dependencies first.

   ```sh
   npm install
   ```

2. Build the website locally.

  ```sh
  hugo serve --open
  ```

## Generating the website

The website can be built into the `public` folder by running

```sh
hugo
```

## Adding a page

A new page can be added by adding a new page (bundle) inside the projects directory by creating
a new folder inside the `/content/projects` directory containing an `index.md` or `_index.md`.
The home page will display the summary parameter of the page bundle front matter. A small logo
used for the homepage display can be specified in the front matter by adding a `logo` page
resource and specifying the image source relative to the diretory. Custom CSS has to be
specified via the `homeLogoCss` variable as shown in the block below:

```toml
homeLogoCss = "satrs-img"
[[resources]]
  name = "logo"
  src = "sat-rs_logo.png"
```

Alternatively, you can specify a text only header using the `homeSummaryHeader` parameter:

```toml
homeSummaryHeader = "spacepackets"
```

The home page template found in `layouts/index.html` will collect all pages inside the
`content/projects` folder and render them accordingly.
