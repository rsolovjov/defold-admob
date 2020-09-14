# Admob extension for Defold

## Documentation

Full documentation can be found here: http://docs.spiralcodestudio.com/extension/admob

## Functions

#### [admob.enable_debug()](http://docs.spiralcodestudio.com/extension/admob/enable_debug)

#### [admob.init()](http://docs.spiralcodestudio.com/extension/admob/init)

#### [admob.load()](http://docs.spiralcodestudio.com/extension/admob/load)

#### [admob.is_loaded()](http://docs.spiralcodestudio.com/extension/admob/is_loaded)

#### [admob.show()](http://docs.spiralcodestudio.com/extension/admob/show)

#### [admob.hide_banner()](http://docs.spiralcodestudio.com/extension/admob/hide_banner)

## Events

#### [admob](http://docs.spiralcodestudio.com/extension/admob/event/admob/)

## Project Settings

To use this extension, open `game.project` and an entry to the `dependencies` property:
* `https://github.com/Lerg/extension-admob/archive/master.zip`

Then select `Project -> Fetch Libraries` to download the extension in your project.

You need to set the AdMob App Id for your iOS and/or Android app in `game.project`. To do so open your `game.project` and add these lines:
```
[admob]
ios_app_id = ca-app-pub-***~***
android_app_id = ca-app-pub-***~***
```

Replace `ca-app-pub-***~***` with your app ids. It can now be viewed or changed in the normal view of the `game.project` file.

You need Defold version 1.2.165+

## Test Ads

ALWAYS use test ads during the development. Only switch to the real ads for submitting to the stores. To enable test ads use `test = true` option in the [admob.init()](http://docs.spiralcodestudio.com/extension/admob/init) call.

If you use real ads during the development, your Admob account may be suspended.

## Demo

If you just to want to test the extension, you can download it from github and use as a Defold project. It will function as a demo. You don't need an Admob account for the demo.

## Usage

Use [admob.init()](http://docs.spiralcodestudio.com/extension/admob/init) to initialize it when your app starts. A good place for that would be the `init()` function of some root game object. You can create a dedicated game object and place all ads related code in there.

Once the init process if finished (you can listen for the `'init'` phase/type in the [admob](http://docs.spiralcodestudio.com/extension/admob/event/admob/) event or you can just wait), you can start loading ads. It's good to preload ads before you actually need to display it. Use [admob.load()](http://docs.spiralcodestudio.com/extension/admob/load) to load and [admob.show()](http://docs.spiralcodestudio.com/extension/admob/show) to show the ads.

When an ad has been closed (phase equals `'closed'`) you can preload next ad.

Banners are displayed automatically when loaded, no need to call [admob.show()](http://docs.spiralcodestudio.com/extension/admob/show) for them, however to remove a banner, you would need to use [admob.hide_banner()](http://docs.spiralcodestudio.com/extension/admob/hide_banner).

## Impressions Share

The extension will serve 1% of all impressions to it's owner benefit. By using this extension you agree with that. Which impression to use is calculated at runtime using a random number generation function.