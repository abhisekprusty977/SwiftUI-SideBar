# SwiftUI SideBar
## Requirements
Platform | Min Deployment Target
:---: | :---:
iOS | 15.0

## Installation
You can add Drawer to an Xcode project by adding it as a package dependency.

1. From the File menu, select Add Packages...
2. Enter "https://github.com/lanarsinc/swiftui-drawer" into the package repository URL text field.
3. Then add `Drawer` directly to your application.

## Basic Usage
You can uses Drawer as a part of your hierarchy like that: 

```swift
struct ContentView: View {

  @State private var isOpened = true

  var body: some View {
    Drawer(
      isOpened: $isOpened,
      menu: {
        ZStack {
          Color.gray

          Button("Hide") {
            isOpened = false
          }
        }
        .frame(width: 100)
      },
      content: {
        ZStack {
          Color.yellow

          Button("Open") {
            withAnimation {
              isOpened = true
            }
          }
        }
        .ignoresSafeArea()
      }
    )
  }
}
```

Also, you may want to control whether menu is being opened and to close it from the menu itself. For this, use an @Environment(\.isDrawerOpened) wrapper to control status of a drawer.

## Things to be done
- Interactive presentation and dismissal via drag.
