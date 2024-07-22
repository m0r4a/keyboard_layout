# This is my keyboard layout repo.

## Add the layout to your system

### Linux

I use Hyprland, a Wayland based Tiling Window Manager, I think if you use Xorg this process should be easier, you can check [ThePrimeagen's layout](https://github.com/ThePrimeagen/keyboards/tree/master/ubuntu) for how to do it in Ubuntu.

1. Copy the layout file to `/usr/share/X11/xkb/symbols/`

```bash
sudo cp linux/moras-programmer-kb /usr/share/X11/xkb/symbols/
```

2. Add the layout in `/usr/share/X11/xkb/rules/evdev.xml`

```bash
sudo nvim /usr/share/X11/xkb/rules/evdev.xml
```

(Below `<layoutList>`)

```xml
    <layout>
      <configItem>
        <name>moras-programmer-keyboard</name>
        <!-- Keyboard indicator for Moras layout -->
        <shortDescription>mo</shortDescription>
        <description>English (Mora)</description>
        <countryList>
          <iso3166Id>US</iso3166Id>
          <iso3166Id>MX</iso3166Id>
        </countryList>
        <languageList>
          <iso639Id>eng</iso639Id>
          <iso639Id>spa</iso639Id>
        </languageList>
      </configItem>
    </layout>
```

3. Add the layout in your hyprland config

```
input {
  xkb_layout "moras-programmer-keyboard"
}
```

Or you can add it alongside the US layout

```
input {
  xkb_layout "moras-programmer-keyboard, us"
  kb_options "grp:alt_space_toggle"
}
```

**Note:** The `grp:alt_space_toggle` option is to switch between the layouts with `Alt + Space`.

4. Reboot

This should be it 

5. Resources

- [ThePrimeagen's layout](https://github.com/ThePrimeagen/keyboards/tree/master/ubuntu)
- [staticf0x's blog post](https://staticf0x.github.io/2021/custom-keyboard-layout-in-x11-and-wayland.html)
- [stingok's blog post](https://blog.stigok.com/2020/10/27/from-x11-xmodmap-to-wayland-xkb-custom-keyboard-layout.html)
