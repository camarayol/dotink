# dotink

A simple lua script for creating symbolic links for dotfiles.

## dependency

[luafilesystem](https://github.com/lunarmodules/luafilesystem)

- installation

```sh
# using pacman on archlinux
sudo pacman -S lua-filesystem

# using luarocks
luarocks install luafilesystem
```

## usage

add symbolic files in `opts.links`

```lua
local opts = {
    links = {
        ['./nvim'] = '~/.config/nvim'
        ...
    },
    -- automaticlly create non-existent directory
    create_directory = true, ---@type true | false

    -- automaticlly remove exist but invalid 'link' files
    remove_invalid_links = true, ---@type true | false
}
```

run `./dotink.lua -i` to create symbolic links, or `./dotink.lua -u` to remove exist symbolic links. (will only remove symbolic links to the origin files).

