# MarioKartPSP Build 20 — N64 Rainbow Road Skybox Integration

This iteration adds a PSP-sized `assets/textures/sky_rainbow_road.png` sky panorama composed from all four supplied N64 Rainbow Road environment textures: cosmos base, rainbow albedo, cubemap environment and emission map. The `RAINBOW ROAD` course (last course in the current 16-course list) uses this sky automatically; Triangle cycles Day/Sunset/Night/Rainbow sky phases on the supported selection screens.

The supplied Mario Kart DS course PNGs are texture atlases, not finished course geometry. All four are included both as originals under `assets/source_course_atlases/` and as small reference copies under `assets/textures/course_atlas_*.png`. They are preserved with the project but are not automatically wrapped onto the existing N64/MK64 track meshes because their matching mesh UV maps are not included in that ZIP.

All original four N64 Rainbow Road skybox source images are preserved under `assets/source_skybox/`. The game only loads the optimized 512x256 composite, so the raw source panoramas do not consume PSP texture-cache memory.

## Repository root
- `main.c`
- `char_models.h`
- `kart_models.h`
- `CMakeLists.txt`
- `Makefile`
- `assets_pack.zip`
- `.github/workflows/main.yml`

GitHub Actions runs PSPDEV and packages `EBOOT.PBP` alongside the unzipped `assets/` directory in the `MarioKartPSP-GAME` artifact.

PSPDEV/hardware testing was not run in this authoring environment; use GitHub Actions to verify the full PSP build.
