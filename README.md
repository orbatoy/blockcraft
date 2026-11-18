# BlockCraft

BlockCraft is a block building game that runs in one web page. You walk around a 3D block world, break blocks and collect them, craft tools and new blocks, build things, trade with villagers and look out for monsters at night.

It works offline. It has no online links, no CDN files and no web fonts. It was made for a tablet screen of 890 x 530 pixels and scales to fit other screens.

> Development with the assistance of AI. Mistakes can occur.

## Run it

1. Download `blockcraft.html`.
2. Open it in a modern web browser. No install and no internet are needed.
3. To share it, upload the single file to a web server or a learning platform.

## How to play

- Break a natural block to collect it. Each natural block you collect becomes unlimited in your block bar.
- Craft everything else. Open the **Craft** button for recipes with pictures and instructions.
- Eat meat to keep your food up. Your health bar drops if you are hurt or starving.
- Place a bed to set where you wake up. At night you can sleep until morning.
- A small goal card at the top left walks new players through the first steps. It can be turned off in Settings.

### Controls

| Action | Touch | Keyboard and mouse |
|---|---|---|
| Move | Drag on the left side | W A S D or arrow keys |
| Look | Drag on the right side | Click the game, then move the mouse |
| Break | Tap a block, or hold the Break button | Left click |
| Place or use | Place button | Right click |
| Jump | Jump button | Space |
| Fly on or off | Double-tap Jump | Double-tap Space |
| Pick a block | Tap a slot | Number keys 1 to 0 |
| Eat | Eat button | E |

Use **Place** on a door, chest, crafting table, furnace, bed or TNT to open, use or light it. Use Place on a villager to trade.

## Worlds

There are two worlds, each with its own save.

- **World 1:** a large world with mountains, caves, sea, ores and gems.
- **World 2:** an almost flat world with a village and villagers. It has a mountain with a cave in one corner, an ocean in another corner, a medieval castle in another corner, and a small cave near the start.

Each world is 256 x 256 blocks. The height of each world is set to 20 blocks above its tallest point.

Every world is made from a seed. The Worlds screen shows each seed. Type the same seed into the New dialog to make the same world again.

## Mining

Blocks take several hits to break. Harder blocks take more hits, and better pickaxes need fewer.

- Coal and iron ore need a stone pickaxe.
- Gems need an iron pickaxe. Gems are found deep underground and in cave walls.
- Iron ore gives Raw iron. Smelt it in a furnace.

| Pickaxe | Speed |
|---|---|
| Hand | 1x |
| Wooden | 1.6x |
| Stone | 2.2x |
| Iron | 3x |
| Gem | 4.5x |

Swords do 2 damage (wooden), 3 (stone), 4 (iron) and 6 (gem). Without a sword you do 1.

## Crafting

A crafting table must be within 5 blocks for everything except planks, the table and torches. Blocks marked with * only need to be collected. They are not used up. Collected crafted blocks can be placed from the block bar and come back when you break them.

| Item | Makes | Ingredients |
|---|---|---|
| Planks | 4 | 1 Wood* |
| Crafting Table | 1 | 4 Planks |
| Torch | 4 | 1 Coal, 1 Wood* |
| Wooden Pickaxe | 1 | 3 Planks |
| Stone Pickaxe | 1 | 3 Stone*, 2 Planks |
| Iron Pickaxe | 1 | 3 Iron, 2 Planks |
| Gem Pickaxe | 1 | 3 Gems, 2 Planks |
| Wooden Sword | 1 | 2 Planks |
| Stone Sword | 1 | 2 Stone*, 1 Plank |
| Iron Sword | 1 | 2 Iron, 1 Plank |
| Gem Sword | 1 | 2 Gems, 1 Plank |
| Glass | 4 | 4 Sand*, 1 Coal |
| Brick | 4 | 4 Stone*, 1 Coal |
| Door | 2 | 6 Planks |
| Ladder | 3 | 2 Planks, 2 Wood* |
| Chest | 1 | 8 Planks |
| TNT | 1 | 1 Coal, 1 Iron, 2 Sand* |
| Bed | 1 | 3 Planks, 3 Leaves* |
| Furnace | 1 | 8 Stone*, 1 Coal |
| Stone Slab | 6 | 3 Stone* |
| Stairs | 4 | 5 Planks |
| Fence | 3 | 2 Planks, 1 Wood* |
| Red Block | 4 | 2 Planks, 1 Brick |
| Blue Block | 4 | 2 Planks, 1 Glass |
| Green Block | 4 | 2 Planks, 1 Leaves* |
| Yellow Block | 4 | 2 Planks, 1 Sand* |
| White Block | 4 | 2 Planks, 1 Snow* |
| Black Block | 4 | 2 Planks, 1 Coal |

**Furnace:** 1 Raw iron and 1 Coal make 1 Iron. 1 Meat and 1 Coal make 1 Cooked meat, which feeds you more.

**TNT:** place it, then use Place on it to light a 3 second fuse. It blasts a crater, sets off nearby TNT and hurts you if you are close.

**Villager trades:** 2 Meat for 1 Coal. 3 Coal for 1 Iron. 5 Iron for 1 Gem. 1 Gem for 3 Iron. 1 Iron for 6 Bricks. 1 Coal for 4 Torches. 2 Iron for 4 Glass.

## Creatures

- **Animals:** pigs, cows, sheep and chickens on land, and fish in the sea. Break them for meat. Animals and monsters do not walk on water.
- **Villagers:** live in the village in World 2. They cannot be hurt.
- **Monsters at night:** zombies, spiders, skeletons that shoot arrows, and creepers that explode. They burn away at dawn and stay out of torchlight. Closed doors stop zombies.

Turn on **Peaceful mode** in Settings to remove monsters and all damage.

## Settings and saving

The Settings button has look speed, sound volume, text size, left-handed layout, Peaceful mode and the goal card. The top row also has Quality (Low, Med or High), Sound on or off, Worlds, New, Save and Help.

Progress saves in the browser with `localStorage`:

- It saves each minute if something changed, and when you leave the page.
- The Save button saves straight away. The status line shows Saved, Unsaved or SAVE FAILED.
- A new world saves only its seed and the blocks you changed, so saves are small.
- Pressing the back button asks "Leave the game?" and saves first.

Keys used: `blockcraft_save_v5`, `blockcraft_save_v5_2`, `blockcraft_slot`, `blockcraft_set`, `blockcraft_q` and `blockcraft_seen`.

## Technical notes

- One HTML file with the CSS and JavaScript inside it.
- No libraries. The 3D view is drawn on a 2D canvas with plain JavaScript.
- Picture quality renders at 200 x 119 (Low), 256 x 152 (Med) or 320 x 190 (High) and scales to the screen. The game lowers the quality by itself if it runs slowly.
- System fonts only. Sounds are made with the browser's Web Audio.
- A day and night cycle takes about 25 minutes.

## Known limits

- It has been checked with simulated tests, not on every browser or tablet. Please test on your own device.
- Saving needs `localStorage`. If a device blocks it or clears it, progress is lost and the game shows SAVE FAILED.
- Saves made before the seed format was added still load, but they stay large.
- The Text size setting uses the browser `zoom` feature. Some older browsers may ignore it.

## Licence
Free for education and other noncommercial use under the PolyForm Noncommercial License 1.0.0. See the `LICENSE` file.
- You can use, copy, share and change BlockCraft for personal, study, hobby and other noncommercial purposes.
- Schools, colleges, charities, public research organisations and government bodies can use it.
- Selling it, or using it in a paid product or service, needs separate permission.
BlockCraft is not affiliated with Mojang or Microsoft.
