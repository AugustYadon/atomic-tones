# atomic-tones: featured trips for Atomic Tones

This repo is served by GitHub Pages at **www.auggodoggogames.com/atomic-tones/**. The app reads
`channels/featured.json` each time it opens, downloads the trips listed there, and drops new ones into
the catalogue. Full notes: `docs/plans/featured-trips.md` in the app's repo. (`.nojekyll` makes Pages serve the
files exactly as they are.)

```
atomic-tones/   (this repo)
  channels/
    featured.json          the list the app reads
  trips/
    first-light.attrip     the trips themselves (made in the app: Share)
    night-drift.attrip
    deep-calm.attrip
```

## Adding one of yours

1. In the app, make the trip in the creator, then **Share** it from the catalogue and save the file
   (Files, AirDrop to the Mac...).
2. Rename it to its id (lowercase letters, digits, dashes), e.g. `solstice-2026.attrip`, and put it
   in `trips/`.
3. Add a line to `channels/featured.json`:

   ```json
   { "id": "solstice-2026", "url": "trips/solstice-2026.attrip" }
   ```

4. Commit and push. Phones pick it up the next time the app opens.

**Taking one down:** remove its line from the list. **A new version** of a trip needs a new id:
phones that have one never download the same id again, and people who deleted it never see it again.

The three starter trips came from the app repo's `Assets/_Scripts/Editor/AtomicTonesStarterTrips.cs`
(Tools > Featured > Write Starter Trips), which writes them into this repo when it sits beside the app
repo (`UnityProjects/atomic-tones`); running it again rewrites them and the list.
