A Docker image for building [Bevy](bevyengine.org) games for the SteamDeck.

Building games for the SteamDeck can be inconsistent because the SteamDeck may not have the newest versions of libraries and cannot be easily updated until Steam releases their update.

The solution is to use one of Valve's containers to build your app in so your app is linked with older versions of libraries that are compatible with SteamOS.

This Docker image simply uses their container and adds Rust and the libraries needed for compiling Bevy apps on Linux.

```
git clone 
docker build 
docker run -v .:/usr/src/project bevy_steamdeck
```
