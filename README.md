# This is my keyboard layout repo.

## Add the layout to your system

### Linux

1. Copy the layout file to `/usr/share/X11/xkb/symbols/`

```bash
sudo cp mora /usr/share/X11/xkb/symbols/
```

2. Add the layout as an english variant in `/usr/share/X11/xkb/rules/base.xml`

(Below English (US) variant)

```xml
<variant>
    <configItem>
        <namel>moras-programmer-kb</name>
        <description>English (Mora version)</description>
        <vendor>m0r4a</vendor>
    </configItem>
</variant>
```

