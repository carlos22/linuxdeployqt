# linuxdeployqt

linuxdeployqt takes an application as input and makes it self-contained by copying in the Qt libraries and plugins that the application uses. It is based on macdeployqt in the tools applications of the Qt Toolkit.

__This is not fully working yet.__ Help is appreciated.

## Installation

* Open in Qt Creator and build
* Build and install [patchelf](https://nixos.org/patchelf.html) (linuxdeployqt uses it to rewrite paths inside the binaries similar to `install_name_tool` on macOS)

## Usage

```
Usage: linuxdeployqt app-binary [options]

Options:
   -verbose=<0-3>     : 0 = no output, 1 = error/warning (default), 2 = normal, 3 = debug
   -no-plugins        : Skip plugin deployment
   -appimage          : Create an AppImage
   -no-strip          : Don't run 'strip' on the binaries
   -use-debug-libs    : Deploy with debug versions of frameworks and plugins (implies -no-strip)
   -executable=<path> : Let the given executable use the deployed frameworks too
   -qmldir=<path>     : Scan for QML imports in the given path
   -always-overwrite  : Copy files even if the target file exists
   -libpath=<path>    : Add the given path to the library search path

linuxdeployqt takes an application as input and makes it
self-contained by copying in the Qt libraries and plugins that
the application uses.
```