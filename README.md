A Docker image for building [Bevy](bevyengine.org) games for the SteamOS (SteamDeck).

Building apps for Linux from your development PC and sharing with another PC can be inconsistent because Linux uses shared libraries and your PC may have linked newer libraries that are incompatible with the target PC's older libraries. This is especially true with the SteamDeck as it may not have the newest versions (e.g. glibc) and cannot be easily updated until Steam releases their official update.

The solution is to build in an environment with older versions of these libraries that are forwards compatible with the new versions to ensure maximum compatibility. Valve provides containers made for doing this.

This Docker image simply uses Valve's Docker image and adds Rust and the libraries needed for compiling Bevy apps on Linux.

# Usage

Build the docker image
```
docker build -t bevy_steamos https://raw.githubusercontent.com/paul-hansen/bevy_steamos_docker/main/Dockerfile
```

From your project directory, run:

```
docker run -v .:/usr/src/project bevy_steamos
```

By default the container will run `cargo build --release` on your project directory. You can find the resulting binary file in the `./target/release` directory

If you want to build a debug build, simply override the default command like this:
```
docker run -v .:/user/src/project bevy_steamos cargo build
```
