# Ozone/Caca

This is copy of the [libcaca](http://caca.zoy.org/wiki/libcaca) port of
[Ozone](https://chromium.googlesource.com/chromium/src/+/master/docs/ozone_overview.md)
that used to be available in the Chromium tree but removed after
[issue 2445323002](https://codereview.chromium.org/2445323002/).

You must install libcaca shared library and development files that are not
provided in the chromium sysroot.
[Get the chromium code](https://www.chromium.org/developers/how-tos/get-the-code)
and execute the following commands inside the `src` repository:

``` shell
git clone https://github.com/fred-wang/ozone-caca ui/ozone/platform/caca
git apply ui/ozone/platform/caca/ozone_extra_caca.patch
gn args out/OzoneCaca --args="use_ozone=1 ozone_platform_caca=1 use_sysroot=0 ozone_auto_platforms=0 toolkit_views=0"
./out/OzoneCaca/content_shell --disable-setuid-sandbox \
                              --ozone-platform=caca \
                              https://www.google.com/chrome/browser/desktop/index.html
```

![Screenshot of chrome download page with Ozone/Caca](https://github.com/fred-wang/ozone-caca/raw/master/ozone-caca.png)
