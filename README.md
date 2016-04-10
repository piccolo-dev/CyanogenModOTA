# CyanogenModOTA
A simple OTA REST Server for CyanogenMod OTA Updater System Application

## How to use
1. `cd /var/www/ && composer create-project julianxhokaxhiu/cyanogenmod-ota CyanogenModOTA`
3. Follow the rest of the tutorial on [my personal blog post](http://blog.julianxhokaxhiu.com/entry/how-the-cm-ota-server-works-and-how-to-implement-and-use-ours) where I explain how to override the build server on your ROM.
4. Optional. If just want to test if the REST Server is working, if you go to [http://localhost/CyanogenModOTA](http://localhost/CyanogenModOTA/) you'll be redirected to the builds directory listing.

## Where do I have to upload the ZIPs that I obtain after the compilation?
- Full builds should be uploaded to `builds/$device/$channel` directory.
- Delta builds will be automatically built on the `builds/delta` directory.

## Can I Debug my REST Server somehow?
Yes, you can! I've implemented a [simple script](https://github.com/julianxhokaxhiu/CyanogenModOTAUnitTest) made for NodeJS that you clone and use it.

## Changelog
### v2.0.4
- Final Fix for TXT and ZIP files in the same directory
- Automatic URL detection for basePath ( no real need to touch it again )
- Delta builds array is now returned correctly

### v2.0.3
- Memcached support
- UNOFFICIAL builds support ( they will be set as channel = NIGHTLY )
- Fix Delta Builds path
- Fix internal crash when *.txt files were present inside /builds/full path

### v2.0.2
- Fix some breaking changes that will not enable the REST server to work correctly.

### v2.0.1
- Excluded hiddens files and autogenerated ones by the OS (for example `.something` or `Thumbs.db`).

### v2.0
- Refactored the whole code.
- Now everything is PSR4 compliant.
- Introduced composer.json to make easier the installation of the project.

## Drawbacks
- Delta updates may or may not work. It's using Deltax3 to create them but it's just experimental. Use it at your own risk.


## License
See [LICENSE](https://github.com/julianxhokaxhiu/CyanogenModOTA/blob/2.0/LICENSE).

Enjoy :)