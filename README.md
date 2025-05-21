# MyST Image Galllery

MyST Image Gallery is a Python [executable plugin][myst-ex-plugin] designed to create felxible image galleries within [MyST Markdown][myst] projects.

## Features

This plugin allows you to easily display collections of images with associated metadata like alt text and tags. Key features include:

* **Dynamic Gallery Generation**: Creates an image gallery by reading metadata from a YAML file.
* **Flexible Image Descriptions**: Provide image descriptions as `alt-text` in the YAML file. This text is displayed under the image in the corresponding card.
* **Customizable Layout**: Images are displayed within MyST cards, organized in a responsive grid. You can control the card size by adjusting the grid's column configuration.
* **Image Styling**: Apply custom CSS styles (like `height`, `width`, `object-fit`) directly to the images for consistent presentation.
* **Tagging System**: Organizes images with user-defined tags, displayed on each image card.

## Installation

To use this plugin, you'll need to set up your project structure and configure MyST.

1.  **Place Plugin File**: Put [image_gallery_plugin.py](./image_gallery_plugin.py) in your project's root directory.
2.  **Organize Image Assets**:
    * Create an [images/](./images/) directory in your project root.
    * Place your image files (e.g., `.jpg`, `.png`) inside the [images/](./images/) directory.
    * Create an [images/images_metadata.yml](./images/images_metadata.yml) file. This YAML will store the metadata for your images, including alt text and tags.
3.  **Register the Plugin in `myst.yml`**: See the [myst.yml](./myst.yml) file in this repository for an example.
4.  **Make Plugin Executable**: On Linux/macOS, grant execute permissions:

```bash
chmod +x image_gallery_plugin.py
```

## Usage

Once installed, simply add the `image-gallery` directive to your MyST Markdown files. The [image-gallery.md](./image-gallery.md) file in this repository serves as an example of how to use the plugin.

Finally, you can preview a rendered version of the image gallery by running the following command from the root of your project:

```bash
myst start
```

## Customization

You can customize the appearance of your image gallery by modifying the `image_gallery_plugin.py` file.

* **Image Styling**: Adjust the `image_style` dictionary within the `render_image` function to control image dimensions and fitting.
* **Gallery Grid Layout**: Change the `grid` column configuration in the `run_transform` function to set how many cards appear per row on different screen sizes.

Refer to the source code for more details on these customization options.

## Credits and Acknowledgements 

This project was inspired by the [cookbook gallery][gallery-pythia] from the [Project Pythia][pythia]. 

[myst-ex-plugin]: https://mystmd.org/guide/executable-plugins
[myst]: https://mystmd.org/
[pythia]: https://projectpythia-mystmd.github.io/
[gallery-pythia]: https://github.com/projectpythia-mystmd/cookbook-gallery