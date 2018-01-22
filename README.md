## About inbestcoin

inbestcoin is a cryptocurrency focused on providing a decentralized mechanism of exchange, and anonymity via untraceable and unlinkable transactions.

You can read more about it at https://coin.inbest.cloud

## Building inbestcoin-gui

### 1. Clone wallet sources

```
git clone git@github.com:inbestcoin/inbestcoin.git
```

### 2. Update git submodules

```
git submodule update --init --recursive
git submodule foreach git pull origin master
```

### 3. Build

#### On Windows

Dependencies: MSVC 2015 or later, CMake 2.8.6 or later, Boost 1.59 or later and QT 5.1 or later.

You may download them from:

* http://www.microsoft.com/
* http://www.cmake.org/
* http://www.boost.org/
* https://www.qt.io/

To build, change to a directory where this file is located, and run these commands:
```
mkdir build
cd build
cmake -G "Visual Studio 14 Win64" ..
```

If you are building on an older processor without AVX support, add the following options to cmake:
```
-DPORTABLE=1 -DWITH_AVX2=0
```

And then build from within MSVC. You may find it helpful to explicitly include Boostand QT paths:
```
cmake -G "Visual Studio 14 Win64" -DCMAKE_PREFIX_PATH="C:\Qt2\5.9.1\msvc2015" -DBOOST_ROOT="C:\boost_1_64_0_built" -DBOOST_INCLUDEDIR="C:/boost_1_64_0_built/lib32-msvc-14.1" -DBOOST_LIBRARYDIR="C:\boost_1_64_0_built\libs"
```

#### On *nix

Dependencies: CMake 2.8.6 or later, Boost 1.59 or later and QT 5.1 or later.

You may download them from:

* http://www.cmake.org/
* http://www.boost.org/
* https://www.qt.io/

```
mkdir build && cd build && cmake -DSTATIC=1 .. && make
```

#### To create a portable build (AppImage), use linuxdeployqt:
```
cp src/intensecoinwallet.desktop build/
cp src/images/intensecoin.png build/
cd build
linuxdeployqt.AppImage intensecoinwallet.desktop -appimage -verbose=2 -always-overwrite -no-translations
```
## Community and support

TBD

## License

inbestcoin is licensed under the GNU Lesser General Public License v3.0
