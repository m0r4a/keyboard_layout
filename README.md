# This is my keyboard layout repo.

## Add the layout to your system

### Linux

1. Copy the layout file to `/usr/share/X11/xkb/symbols/`

```bash
sudo cp moras-programmer-kb /usr/share/X11/xkb/symbols/
```

2. Add the layout in `/usr/share/X11/xkb/rules/evdev.xml`

(Below <layoutList>)

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

3 Add the layout in your hyprland config

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
