<!-- PEANUTS: new profile, provisional -->
# FINAL FANTASY II Pixel Remaster (`01006B7014156000`)

Base game 1.0.0 (`v0`), SDK 14.3.0. **Unity** (IL2CPP) with FMOD, rendering with **NVN**, 64-bit (`check-arch` printed `RESULT: ARCH64 programs=1`). The survey found Unity 2019.3.15f1 and 2020.3.37f1 strings in `main`. Modules `main`, `subsdk0` (NintendoSDK_movie) and `sdk`. The closest profile is [Chained Echoes](../0100C510166F0000/README.md) (Unity 2020.3.36f1, SDK 14.3.0, the same three modules). The other five FINAL FANTASY Pixel Remaster games have the same engine, SDK and module set; each has its own profile.

## Status

**Provisional.** The profile is the survey's: `scripts/build_ipa_from_nsp.py` with `dm/games/profile_guess.py` wrote `game.tsv` and `shader_split.py` wrote the shader tables beside it. Nothing in it was checked by hand. It has not been started on a device yet. It is not in any list of supported games.

## Builds

| Module | Build ID |
|---|---|
| `main` | `635ed7043704db9c944d4aaa2a2b61ed` |
| `subsdk0` | `c781dd63daf0ddcdb9975da50a198f93` |
| `sdk` | `2aef2cffb104ee7c9e212fd2f4c731e9` |

The display version is the base game's: 1.0.0, `v0`. Only the base game is packed: the profile's `build`, `package` and `shader_versions` rows all say `v0`. The dump has no update and no DLC. The RomFS has 969 files, 0.54 GB.

## Shaders

- `shader_split.py` found 1,733 programs: 56 compute, 1 geometry, 840 pixel, 836 vertex, and printed no `[RED]` line.
- By source: 1,722 in `data` (UnityFS bundles under `Data/`, `shader_groups /Data/=data`) and 11 in `main`, from its 11 GLSLC compiler output magics.
- `shader_pairs.tsv` has 836 variation pairs.

## Memory

The keys are the survey's, as generated. The heap check that would correct them runs on a Mac and did not run here (this profile was made on Linux).

| Setting | Value |
|---|---|
| `mem_reserve` | `0x140000000` |
| `mem_alias` | `0x118000000` |
| `mem_stack` | `0x10000000` |
| `app_pool` | `0xCD500000` |
| `sys_resource` | `0x1000000` (read from the NPDM: 16 MB of system resource) |

## Found on this game

- `romfs_marker` is `ff2_bgm_13_assets_all.bundle`, a file named for this game. The survey's first guess was `ff6_battle_effect_assets_all.bundle`, which every one of the six Pixel Remaster RomFS holds, so it could not tell the games apart.
- The survey names no Unity 2018 player, so the stream-buffer start hang that [Pokémon Mystery Dungeon: Rescue Team DX](../01003D200BAA2000/README.md) has is not expected here. That is a reading of the survey, not a measurement.

## Open

- Everything past a first start is untested: a new game, saves, battles, movies, sound, docked mode, and the system driver against Turnip.
- The memory keys and `romfs_marker` are guesses until a long run confirms them.
- No update or DLC build row, because the dump has none.
