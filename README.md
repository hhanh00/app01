# app01

A new Flutter project.

## How to make a flutter/rust project

1. create project `flutter_rust_bridge_codegen create app01`
    - add `build-win.yaml`
1. add fastforce to `build-win.yaml`, remove flutter build
    - rename appname
    - add `windows/packaging/exe`
        - `make_config.yaml`, `setup.iss`
    - add `distribute_options.yaml`
1. add android
    - create JKS file
    - add `build-android.yaml`
        - rename appname
        - rename keyalias
    - modify `app/build.gradle.kts`
    - add *repository secrets*
1. add linux & mac
    - add `assets/logo.png`
    - add `linux/packaging/deb`
        - `make_config.yaml`
        - `app.appdata.xml` (rename too)
    - add `misc`
        - add `app.json`
        - add `codesign-notarize.sh`
1. update `pubspec.yaml`
    - update `CMakefiles.txt` for linux and turn off c++ unused var warnings
1. install release please and cleanup
    - copy `ci` and `release-please.yaml`
    - copy release-please `config` and `manifest`
    - reset version in manifest
    - delete test and integration dart folders

Test a release

