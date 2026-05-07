# Tektite Video Combiner 15.0

Standalone ComfyUI custom node variant with a new class name so it can be installed next to older versions without conflicts.

## Node Name
- `Tektite Video Combiner 15.0`

## Key Features
- `clip1..clip16` inputs
- Accepts video paths, `.mp4`, single `.png`, PNG folders/globs, image sequences, and Comfy `IMAGE` batches
- Prefers `.mp4` over preview `.png` when upstream combine nodes output both
- Normalizes final stitched output to a fixed 1280x720 canvas
- Defaults to 25 fps and preserves every decoded frame when source FPS already matches `sequence_fps`
- Remaps only mismatched-FPS clips to `sequence_fps` while preserving source duration
- Preserves input slot order (`clip1`, `clip2`, ...)
- Wait/poll logic with timeout and stable polls
- Optional `audio` input for final mux

## Outputs
- `video` (VIDEO)
- `path` (STRING)

## Output Path
- Leave `output_path` empty to write `stitched_TIMESTAMP.ext` directly into the normal ComfyUI output folder.
- Set `output_path` to a folder or file path when you want to control the destination.

## Install
1. Copy this folder into `ComfyUI/custom_nodes/`
2. Restart ComfyUI
3. Add node: `Tektite Video Combiner 15.0`

## Notes
- This package intentionally uses a different backend class (`TektiteVideoCombiner15`) so it can live next to older versions.
