# Persona3D for iPhone

A native SwiftUI shell (WKWebView, iOS 17+) around the live web app at https://persona3d-phi.vercel.app, generated from the
[Kolam iOS shell template](https://github.com/tgopinath/kolam-design-system/tree/main/ios/shell-template).
Inside this app the page switches to Apple's Human Interface Guidelines look (Kolam iOS kit: large titles,
Liquid Glass tab bar, back + inline title, haptics); in Safari or any other browser it keeps its own web look.
Camera and photo-library usage strings are set, so reference photos can be taken in a private deployment
(the public demo shows a sample character and does not accept photos).
Web app source: https://github.com/tgopinath/persona3d

<img src="screenshots/home.jpg" width="200" alt="Home"> <img src="screenshots/create.jpg" width="200" alt="Create"> <img src="screenshots/library.jpg" width="200" alt="Library">

## Run it

```sh
xcodebuild -project Persona3D.xcodeproj -scheme Persona3D \
  -destination 'platform=iOS Simulator,name=iPhone 17 Pro' -derivedDataPath build CODE_SIGNING_ALLOWED=NO build
```

Then install `build/Build/Products/Debug-iphonesimulator/Persona3D.app` with `xcrun simctl install booted …`.
Debug builds accept `-KolamStartURL "<url>"` (open another route) and `-KolamJS "<line>"` (run one line of
JavaScript after the first load) on `simctl launch`, for screenshots.
Installing on other people's iPhones needs TestFlight or the App Store (Apple Developer Program).
