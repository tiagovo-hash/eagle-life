# Eagle Life

A 3D game where you live as a bald eagle: survive the forest, build a nest and raise a family. Made by Tiago Valent for iPad, iPhone and the web.

- **Play:** https://tiagovo-hash.github.io/eagle-life/
- **Privacy policy:** https://tiagovo-hash.github.io/eagle-life/privacy.html
- **Support:** https://tiagovo-hash.github.io/eagle-life/support.html
- **Contact:** tiagovo@icloud.com

On iPad, open the game in Safari, tap Share and choose **Add to Home Screen** to play full screen.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole game in one file. three.js and the fonts are embedded, so the page loads nothing from other servers. |
| `privacy.html` | Privacy policy in English and Portuguese. Use this URL in App Store Connect. |
| `support.html` | Help, FAQ and contact in English and Portuguese. Use this URL in App Store Connect. |
| `CREDITS.md` | Credits and the licenses of three.js and the Barlow fonts. |

## Privacy

The game collects no personal data: no accounts, ads, analytics, tracking or purchases. Progress, achievements, the ranking and the player name are saved only on the player's device, in `localStorage` under the key `eaglelife.save.v1`. In the game, **About → Reset progress** erases them.

For the App Store privacy label this means **Data Not Collected**, as long as the app keeps no server, ads or analytics. Check it again before adding any online feature.

Links that leave the game (privacy policy and support) are behind a parental gate.

## Ranking and achievements

Today the ranking (10 best scores and 10 fastest forest times) and the 15 achievements are saved on the device. The game already reports every score and achievement to a bridge, so the App Store version can send them to Game Center:

- a `eaglelife:gamecenter` event on `window`, with `detail = { type, id, value }`;
- `window.EagleLifeGameCenter.report(detail)`, if a native wrapper defines it.

`type` is `"score"` or `"achievement"`. Achievements are reported with `value: 100` (percent complete).

### Leaderboards to create in App Store Connect (or in Xcode's Game Center configuration)

| Leaderboard ID | Name | Sort | Score format |
| --- | --- | --- | --- |
| `com.tiagovalent.eaglelife.score` | Best Score | High to low | Integer |
| `com.tiagovalent.eaglelife.forest_time` | Fastest Forest | Low to high | Elapsed Time – To the Hundredth of a Second (the game sends centiseconds) |

### Achievements to create in App Store Connect

| Achievement ID | Name | How to unlock | Suggested points |
| --- | --- | --- | --- |
| `com.tiagovalent.eaglelife.ach.first_drink` | Fresh Water | Drink from the lake | 10 |
| `com.tiagovalent.eaglelife.ach.first_catch` | First Catch | Catch your first prey | 10 |
| `com.tiagovalent.eaglelife.ach.fisher` | Fisher Eagle | Catch a fish from the lake | 20 |
| `com.tiagovalent.eaglelife.ach.hunter` | Skilled Hunter | Catch 10 animals | 40 |
| `com.tiagovalent.eaglelife.ach.treetop` | Treetop Lookout | Land on the top of a tree | 20 |
| `com.tiagovalent.eaglelife.ach.high_flyer` | High Flyer | Fly 200 m above the ground | 30 |
| `com.tiagovalent.eaglelife.ach.speed_dive` | Speed Dive | Dive faster than 130 km/h | 30 |
| `com.tiagovalent.eaglelife.ach.sharp_eyes` | Sharp Eyes | Use Eagle Eye 5 times | 20 |
| `com.tiagovalent.eaglelife.ach.nest_builder` | Home Builder | Finish building the nest | 50 |
| `com.tiagovalent.eaglelife.ach.life_partner` | Life Partner | Win over a mate | 60 |
| `com.tiagovalent.eaglelife.ach.proud_parent` | Proud Parent | Watch your egg hatch | 80 |
| `com.tiagovalent.eaglelife.ach.forest_family` | Forest Family | Complete the forest | 100 |
| `com.tiagovalent.eaglelife.ach.swift_wings` | Swift Wings | Complete the forest in under 15 minutes | 100 |
| `com.tiagovalent.eaglelife.ach.explorer` | Explorer | Fly 20 km in total | 60 |
| `com.tiagovalent.eaglelife.ach.survivor` | Survivor | Stay alive for 20 minutes in one game | 70 |

The suggested points add up to 700. Game Center allows up to 100 points per achievement and 1,000 points per game.

## Points

| Action | Points |
| --- | --- |
| Water bar full the first time | 20 |
| Rabbit eaten | 30 |
| Fish eaten | 25 |
| Stick added to the nest | 15 |
| Nest finished | 50 |
| Mate won over | 80 |
| Back home with your mate | 60 |
| Egg hatched | 120 |
| Chick fed | 40 |
| Forest complete | 300, plus 1 point for every 2 seconds under 15 minutes |

## Versions

- **0.4** (October 2026): score, achievements and ranking on the device, How to play, About and credits, privacy policy and support pages, parental gate, fonts embedded in the page.
- **0.3**: realistic 3D eagle and forest; tap an animal to hunt it and tap again to eat; tap the water to drink; camera centred on the eagle.
- **0.2**: landing, walking and taking off.
- **0.1**: first prototype.

## Credits and licenses

- 3D engine: [three.js](https://threejs.org) r159, MIT License, Copyright © 2010-2023 three.js authors.
- Fonts: [Barlow and Barlow Condensed](https://github.com/jpt/barlow) by Jeremy Tribby, SIL Open Font License 1.1, Copyright 2017 The Barlow Project Authors.
- Full license texts: [CREDITS.md](CREDITS.md).

The game's code, models, textures and sounds are made by the game itself. © 2026 Tiago Valent. All rights reserved.
