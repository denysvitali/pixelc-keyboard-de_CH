### denvit's Keyboard

The original author is the Google Software Engineer Rudolf Polzer. This project is a fork of [google/us-altgr-intl](https://github.com/google/us-altgr-intl).

This package contains additional layout files for physical keyboards (i.e. USB,
Bluetooth) to enhance the original Pixel C Swiss German Keyboard Layout.

### The Layouts

The layout is based on the existing Swiss German layouts, with
the following changes:

- `AltGr + L` prints `$`
- `AltGr + 0` prints `^` (the correct one)

### Compiling & Installing

```
./gradlew installDebug
```

In case of a Pixel C, additionally run one of:

```
adb shell pm disable-user com.android.dragonkeyboard
```

After that, to to Settings / Language & input / Physical keyboard and select the keyboard layouts from this package. They will show up as layouts provided by "US AltGr International External Keyboard Layout".

Pixel C users: to go back to using the layouts included with the device, run one
of:

```
adb shell pm enable com.android.dragonkeyboard
```

### Adding Your Own

To add a custom layout:

1. Download one of the existing layout files from
   [AOSP](https://android.googlesource.com/platform/frameworks/base/+/master/packages/InputDevices/res/raw)
   or
   [Pixel C](https://android.googlesource.com/device/google/dragon/+/marshmallow-dr-dragon-release/DragonKeyboard/res/raw/).
1. Edit and rename the file as needed. Some ideas:
   1. You can change the symbols on a key by simply editing the `key` blocks in
      the file. Should be quite self-explaining.
   1. You can remap/swap keys by adding lines of the sort
      `map key <scancode> <keyname>`, where the scancode and keyname come from
      [Generic.kl](https://android.googlesource.com/platform/frameworks/base/+/master/data/keyboards/Generic.kl).
1. Save it below `res/raw/` in this repository.
1. Duplicate and edit one of the existing entries below
   [keyboard\_layouts.xml](res/xml/keyboard_layouts.xml) according to the new file name.
1. Duplicate and edit one of the existing entries in
   [strings.xml](res/values/strings.xml) according to the new file name.
1. Compile and install as above.

### Copyright

See the `LICENSE` file.

### Contributing

See the `CONTRIBUTING.md` file.

### Disclaimer

This is not an official Google product.
