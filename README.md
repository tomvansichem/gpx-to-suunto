# Turn-by-turn for Suunto

Routes planned in Strava, Komoot, Garmin Connect and most other planners arrive in the Suunto app without turn waypoints, so the watch gives no turn-by-turn navigation. This page takes such a GPX (track or route) and writes it out in the format Suunto's own route planner uses, with a turn waypoint at every turn it finds.

Everything runs in the browser. The file is never uploaded.

## Use it

Open `index.html` in a browser, or serve the folder with any static file server:

```sh
python3 -m http.server
```

Choose a GPX, check the map, download the result and import it in the [Suunto Routeplanner](https://routeplanner.suunto.com/). The settings under "Adjust turn detection" control how sensitive the turn detection is.

## How it works

All the logic is in `index.html`. The block between `CORE-START` and `CORE-END` has no DOM access: it cleans and simplifies the points, detects turns by comparing the bearing a set distance before and after each point, and builds the GPX with Suunto's turn types and `suunto-rp:waypointIndices` extension. The rest of the script is the interface.

## As is

This is a free tool without support. It has only been tried on one watch. Issues and pull requests are not accepted. Fork it if you want to change it.

Not affiliated with or endorsed by Suunto. Suunto is a trademark of Suunto Oy.

## License

MIT for the code, see [LICENSE](LICENSE). The Big Shoulders Display font is under the [SIL Open Font License](fonts/OFL.txt).
