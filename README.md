A Docker image for building [Bevy](bevyengine.org) games for the SteamDeck.

Building games for the SteamDeck can be inconsistent because the SteamDeck may not have the newest versions of libraries and cannot be easily updated until Steam releases their update.

The solution is to use one of Valve's containers to build your app in so your app is linked with older versions of libraries that are compatible with SteamOS.

This Docker image simply uses Valve's container and adds Rust and the libraries needed for compiling Bevy apps on Linux.

# Usage

Build the docker image
```
git clone https://github.com/paul-hansen/bevy_steamdeck_docker.git
cd bevy_steamdeck_docker
docker build -t bevy_steamdeck .
```

From your project directory, run:

```
docker run -v .:/usr/src/project bevy_steamdeck
```

By default the container will run `cargo build --release` on your project directory. You can find the resulting binary file in the `./target/release` directory
