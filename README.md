# Silent Ward

A first-person horror game that runs in a single HTML file. The power is out in Ward 13, something is wandering the halls, and you have a flashlight with a battery that won't last.

Find four fuses, get the power back on, and reach the exit door before the Patient finds you.

## How to run it

Download `index.html` and double-click it. It opens in your browser, and Chrome or Edge works best.

There's nothing to install and no internet connection needed. It doesn't use any libraries or image files, so the whole game is that one file.

When the title screen shows up, press **Enter**. Then click on the game window so the mouse gets captured for looking around. If you press Esc, the browser lets go of your mouse, so just click the game again.

## Controls

| Key | What it does |
|---|---|
| W A S D | Move |
| Shift | Run (uses stamina, and it's loud) |
| Mouse | Look around |
| Arrow keys, or Q / E | Turn, if the mouse isn't working for you |
| F | Flashlight on/off |
| Enter | Start, or try again after dying or winning |

## How it plays

You start in the top-left corner of a maze of corridors. The maze is different every time you play, and so is the position of everything in it.

You need to find **4 glowing yellow fuses**. They're placed far from where you start, so you will have to explore. Blue glowing orbs are flashlight batteries, and each one gives some charge back. Your flashlight drains the whole time it's on, and when it runs out you're nearly blind, so use it carefully.

Once you have all four fuses, the red EXIT door in the bottom-right corner turns green and unlocks. Walk into it to win. Before that it's dead, and walking into it just tells you how many fuses you're still missing.

### The Patient

There's one monster, and it never stops walking. It does two things:

- **It sees you.** If it has a clear line of sight within a few tiles, it chases you.
- **It hears you.** Running can be heard from far away, walking from closer, and standing still is almost silent. This is why you can't just sprint everywhere.

It gets a little faster for every fuse you pick up, so the second half of the game is harder than the first. You do get about eight seconds of peace at the start before it starts looking for you.

If it loses you for a few seconds it goes back to wandering. If it catches you, that's the end of the run.

You'll know it's near because you'll hear a heartbeat, the screen starts to shake, the edges turn red, and a pair of red eyes shows up in the dark before you can see the rest of it. There are also random whispers and low thuds every so often, even when it's nowhere close.

## Tips

- Walk by default and only run when you're being chased
- Stop and listen when you hear the heartbeat. Standing still is your best way of disappearing
- Don't leave the flashlight on in corridors you already know
- Dead ends are bad places to be

## How it works

I'm a beginner, so here's what I understand of how this is built:

- The 3D view is a **raycaster**, the same idea as old games like Wolfenstein 3D. For every column of pixels on the screen, the game shoots a ray into a 2D grid map, finds the wall it hits, and draws a strip of wall that's taller when it's close and shorter when it's far. So it looks 3D, but it's really a flat map.
- The monster and the items are flat pictures (sprites) that always face you.
- The maze is made with a randomized depth-first search, and then a few extra walls get knocked out so there are loops to run around in.
- The monster finds you by working out the shortest path through the maze to where you're standing.
- All the textures (bricks, blood stains, doors, the monster) are drawn with code on a canvas when the game starts.
- All the sounds, like the hum, heartbeat, footsteps and whispers, are made with the browser's Web Audio API. There are no sound files.

## Things that aren't great yet

- It's drawn on a 2D canvas, so it can run slowly on old computers or phones
- The monster can sometimes get stuck on corners for a moment
- Keyboard and mouse only. There's no gamepad or touch support
- No save, no settings menu, no volume control


You can play out this game at - https://hardik19april-eng.github.io/danger_horror/




<img width="1911" height="1026" alt="Screenshot 2026-11-05 160737" src="https://github.com/user-attachments/assets/9de4c8ed-0b8a-4904-b329-7fa691e39cc1" />
<img width="1891" height="1015" alt="Screenshot 2026-11-11 141041" src="https://github.com/user-attachments/assets/9a637ffa-c61b-485c-b6b2-3b9b792b940d" />
