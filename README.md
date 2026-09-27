# MP3 Player CLI

A menu-driven MP3 player simulation written in C, built around a custom
doubly linked list to manage a playlist. This project focuses on manual
memory management and pointer-based data structures rather than actual
audio playback.

## Overview
This program loads a playlist from a text file into a doubly linked list,
then presents a menu-driven interface for browsing, playing, and adding
songs. "Playback" is simulated (no real audio is played) — the focus of
this project is implementing and managing the underlying data structure
correctly in C, using raw pointers and manual memory allocation.

## Features
- **Doubly linked list playlist** — each song node stores `next` and `prev`
  pointers, enabling both forward and backward navigation
- **Circular navigation** — reaching the end of the playlist with "Play Next"
  wraps back to the first song; reaching the beginning with "Play Previous"
  wraps to the last song
- **File-based playlist loading** — parses a comma-separated `Music.txt` file
  (`Title,Artist,DurationMs`) into linked list nodes using `strtok()`
- **Add songs at runtime** — appends new songs to the end of the list via
  user input
- **Simulated playback** — prints a live "now playing" progress indicator
  (dots accumulating over time) scaled down from the song's real duration
- **Random song selection** — picks and plays a random song from the playlist
- **Manual memory management** — every node is dynamically allocated with
  `malloc()` and explicitly released with `free()` on exit, with null checks
  throughout to guard against failed allocations and empty-list edge cases

## Menu Options
1. View Playlist
2. Play Full Playlist
3. Add a Song to the Playlist
4. Play First Song Only
5. Play Next Song
6. Play Previous Song
7. Play a Random Song
8. Exit

## Playlist File Format
`Music.txt` must be in the same directory as the executable, with one song
per line in the format:

```
SongTitle,Artist,DurationInMilliseconds
```

Example:
```
Just Like Heaven,The Cure,500
Fast Car,Tracy Chapman,2000
```

## How to Build and Run

### macOS (Terminal)
Make sure you have Xcode Command Line Tools installed (includes `gcc`/`clang`):
```bash
xcode-select --install
```
Then compile and run:
```bash
gcc mp3player.c -o mp3player
./mp3player
```

### Linux (Terminal)
Make sure `gcc` is installed:
```bash
sudo apt update && sudo apt install gcc      # Debian/Ubuntu
sudo dnf install gcc                          # Fedora
```
Then compile and run:
```bash
gcc mp3player.c -o mp3player
./mp3player
```

> **Note:** Make sure `Music.txt` is in the same directory as the compiled executable before running the program.

## Technical Highlights
- Implemented all list traversal (forward, backward, wraparound) manually
  using raw pointers — no arrays or built-in containers
- Designed defensive null checks before every pointer dereference to prevent
  segfaults on edge cases (empty playlist, single song, malformed file lines)
- Manually traced every `malloc()` call to a matching `free()` in
  `freePlaylist()` to confirm there were no memory leaks

## What I Learned
Building the playlist structure from scratch, instead of using a built-in
list, forced a much closer look at how linked data structures are
represented and manipulated in memory, and how much more discipline manual
memory management requires compared to garbage-collected languages.
