# ShiftBypass

![Latest release](https://img.shields.io/github/v/release/0softwaredevelopment0/ShiftBypass)

A tiny client-side Fabric mod for Minecraft **26.2** that removes the vanilla rule
which stops you from sneaking while you are "busy" - chatting, browsing your
inventory, using a crafting table, furnace, chest, etc.

With ShiftBypass enabled, pressing shift **always** reaches the game, and it follows
your vanilla sneak settings: if sneak is set to *Toggle* in the vanilla controls, it
toggles; if it is *Hold*, it holds.

## Usage

```
/sb            - show current state
/sb on         - enable the bypass
/sb off        - disable the bypass
/shiftbypass   - alias for /sb
```

The command is a client-side command (works in singleplayer and on any server,
no server permission needed). The bypass starts **off** every launch - run
`/sb on` after joining a world.

## How it works

While a screen is open, vanilla's keyboard handler never presses game key mappings -
it only routes keys to the screen. The mod injects at the head of that handler and,
for shift presses while a screen is open, presses the vanilla sneak key mapping
directly. Because it uses the mapping's own `setDown` logic, toggle/hold behavior
stays exactly as you configured it in vanilla options.

## Building

Requires JDK 25:

```
./gradlew build
```

The jar lands in `build/libs/shiftbypass-1.0.0.jar`.

## License

AGPL-3.0
