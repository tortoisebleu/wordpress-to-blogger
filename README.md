# Hikkoshi Hikyaku: Ameba Ownd to Blogger Converter

A single-file, browser-based tool that converts WordPress-format XML exports from **Ameba Ownd** into **Blogger-importable XML**.

Ameba Ownd lets you export your posts only as WordPress-format XML (or Ameba Blog text format), and Blogger cannot import that directly. This tool fills the gap: load the exported files, press a button, and import the resulting file with Blogger's own *Import content* feature.

> The interface is in Japanese. "引っ越し飛脚" (Hikkoshi Hikyaku) roughly means "moving-house courier".

## Features

- **Converts WordPress export XML to Blogger Atom XML**, keeping titles, bodies, dates and authors
- **Merges many files in one run.** Ameba Ownd splits large exports into many XML files; select several at once and get a single Blogger XML
- **Optional draft inclusion** (private and unpublished posts)
- **Optional line-break repair** for plain-text posts that have no HTML tags, so lines do not collapse into one block
- **Optional WordPress markup cleanup**
  - removes `<!-- wp:... -->` block comments
  - converts `<figure class="wp-block-image">` to `<div class="separator">`
  - removes `wp-block-*` and `wp-image-*` classes
  - removes trailing `<br />` and `&nbsp;` in paragraphs
  - sets `loading="eager"` on the first image of each post only
  - keeps empty-line paragraphs unless you tell it not to
  - checks that every post's image URLs are unchanged after cleanup, and keeps the original HTML for any post that fails the check
- **Block survey**: shows how many of each WordPress block type (`paragraph`, `heading`, `image`, ...) were found, so you can spot content the tool does not handle yet
- **Image helpers**: list all image URLs (CSV or TXT) and save the images as a ZIP

## Important: images are not migrated

The converted posts still point to the image URLs on Ameba Ownd's servers. Those images may stop loading once the service shuts down. Save your images (ZIP button) before that, and plan where they will live afterwards, for example by re-uploading them to Blogger.

Ameba Ownd's image server may block direct downloads from the browser (CORS). Images that cannot be fetched are listed in `failed_image_urls.txt` inside the ZIP, and you can use the URL list with a bulk downloader instead.

## Usage

1. Export your site from Ameba Ownd (WordPress format) and unzip it. You will get one or more `.xml` files.
2. Open the HTML file from this repository in a modern browser. No installation or build step is needed.
3. Select the XML files. Files are sorted by name and merged. The author tested it with batches of 30 to 40 files at a time.
4. Choose the options you need.
5. Download the converted XML.
6. In Blogger, go to *Settings > Manage blog > Import content* and select the file.

Tip: try one file on a throwaway blog first. If you turn off *Automatically publish all imported posts and pages*, the imported posts arrive as drafts, which makes checking easy.

## Privacy

Your export files are processed locally in your browser and are never uploaded. The page does load a few resources from the internet: Tailwind CSS and Google Fonts for the layout, and JSZip from cdnjs for the ZIP feature. When you press the ZIP button, your browser also fetches your images directly from Ameba Ownd.

## Limitations

- Only tested with Ameba Ownd exports. Other WordPress exports may work but are not supported.
- Images are not copied to Blogger.
- Blocks other than paragraph, heading and image are kept as they are; check the block survey to see whether you have any.
- Images get no `width` / `height` attributes, so wide images can overflow the default Blogger template. Adding `.post-body img { max-width: 100%; height: auto; }` to the template's CSS fixes this.

## Contributing

Issues and pull requests are welcome.
