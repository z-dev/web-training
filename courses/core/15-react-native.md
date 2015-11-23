# React
# Outcome

You'll:

* Be able to build an App. (What?!)

# Advice

React Native is like React for the web, but for iOS and Android.

##Differences

* HTML is replaced with an iOS / Android specific markup. It looks like HTML e.g `<div> -> <view>`, `<p> -> <text>`.
* No CSS. CSS is replaced by very similar 'styles' (javascript hashes). They're a subset of CSS, and only support the flexbox layout.
* The thing runs as an App on an iPhone (or the iPhone simulator) or an Android (or the simulator)
* You can't escape the development environment for iPhone. You still need XCODE which is used write Apps.

##Similarities

* React-Native is really similar to React. You write components with state + props and a render function (nothing changes there).
* 99% of your code will be Javascript. You shouldn't have to write any Objective C (but you can if there's something which is impossible)
* npm, requiring javascript files, any npm module (lodash, superagent etc. etc.), JSX

##How it works

React-Native comes with a command line cli (which is `npm install`ed). You can run `react-native init MyProjectName` and it generates all the files you need. A project which you can open and run in XCode. When you run the project xcode a couple of things happen:

* A `webpack` watch kind of thing starts
* It launches the emulator with your project in.

What is happening is that an iOS app (which is normally written in objective-c or swift (their new language)) launches. Internally the app then loads a javascript engine (which comes with iOS) just like the one in Safari. It then executes all your javascript / react-native code in that javascript engine. React-Native calls the render method to decide how the app should look. Whereas React (for web) would have run some jQuery-like code to modify the DOM, react-native runs some objective-c code to make the screen look as it should. When 'state' changes in a component, the render method is fired it calculates what the screen should look like vs what is currently looks like, it runs a bit of objective C to make the change etc. etc. This means the app is actually running in Objective C, and means it looks and feels like a native app [1].

There are two engines react-native can use. The built in iOS javascript engine (JavaScriptCore, which powers safari), or it can attach to an external browser using *magic* e.g. Chrome.

You can't fully escape xcode. Lots of settings about your app stay in xcode. If you want to add an image to the app (that is stored locally with the app), you add it in Xcode etc. But mainly you just fiddle with settings, you don't use code.

## Alternative markup (Built in components)

Look in the components section (on the left) in the Docs. I suggest checking out the example [UIExplorer app](https://github.com/facebook/react-native/tree/master/Examples/UIExplorer) and running it to see visually what each thing does.

## Styles

[Read this page](https://facebook.github.io/react-native/docs/style.html#content). Click on the links at the bottom. Each built-in component has a list of styles which you can use.

Styles are hashes, and so are just code. You can use lodash to manipulate them (for example `_.merge` is kind of like a Sass `@extend`)

## Practical advice for developing

### Your default dev flow

* Open xcode project
* Hit run (It will launch your app in iOS simulator)
* Attach to Chrome rather than JavaScriptCore (this gives you chrome dev tools like normal :) ) (Apple+Z (or D?) opens a menu to let you do this)
* Open the code base in sublime (XCode sucks IMO) and edit code.
* Press Apple+R to reload app after making a change.

### It's not working what do I do.

I've seen it break for no reason at all. If that happens and you're unsure follow these steps.

* Close the packager window that pops up initally.
* Close all Chrome Dev Tools attached to the app.
* Press stop in XCode
* Now start over from scratch.


# Learning materials

# Core

* [React Native Docs](https://facebook.github.io/react-native/docs/getting-started.html)

# Tasks

* Read the native docs
* Get the UIExplorer example working.

[1] Other frameworks instead pretend to be an app. But they're actually loading a web-browser, this has the advantage you could use bootstrap, but is often a bit clunky (poor performance).
