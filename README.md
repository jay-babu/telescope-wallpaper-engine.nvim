# Telescope-media-files.nvim
Preview images, pdf, epub, video, and fonts from Neovim using Telescope.

![Demo](https://i.imgur.com/wEO04TK.gif)

## Install
```viml
Plug 'nvim-lua/popup.nvim'
Plug 'nvim-lua/plenary.nvim'
Plug 'nvim-telescope/telescope.nvim'
Plug 'nvim-telescope/telescope-media-files.nvim'

```
## Setup

``` lua
require('telescope').load_extension('wallpaper_engine')

```

## Configuration
This extension can be configured using `extensions` field inside Telescope
setup function.

```lua
require'telescope'.setup {
  extensions = {
    wallpaper_engine = {
      -- filetypes whitelist
      -- defaults to {"png", "jpg", "mp4", "webm", "pdf"}
      filetypes = {"png", "webp", "jpg", "jpeg"},
      -- find command (defaults to `fd`)
      find_cmd = "rg"
    }
  },
}
```

## Available commands
```viml
:Telescope wallpaper_engine

"Using lua function
lua require('telescope').extensions.wallpaper_engine.wallpaper_engine()
```

When you press `<CR>` on a selected file, it will copy its relative path to the clipboard


## Prerequisites
* [Chafa](https://hpjansson.org/chafa/) (required for image support)
* [ImageMagick](https://imagemagick.org/index.php) (optional, for svg previews)
* [fd](https://github.com/sharkdp/fd) / [rg](https://github.com/BurntSushi/ripgrep) / [find](https://man7.org/linux/man-pages/man1/find.1.html) or fdfind in Ubuntu/Debian.
* [ffmpegthumbnailer](https://github.com/dirkvdb/ffmpegthumbnailer) (optional, for video preview support)
* [pdftoppm](https://linux.die.net/man/1/pdftoppm) (optional, for pdf preview support. Available in the AUR as **poppler** package.)
* [epub-thumbnailer](https://github.com/marianosimone/epub-thumbnailer) (optional, for epub preview support.)
* [fontpreview](https://github.com/sdushantha/fontpreview) (optional, for font preview support)

credit to https://github.com/cirala/vifmimg
