# Clear_data

Cleaned 276-scene annotation package for the SUNRGBD smart-home RGB-D project.

This folder intentionally does **not** include the SUNRGBD dataset itself. Teammates should download SUNRGBD separately and place it at the local path used by the CLI.

## Key Files

- `annotations/clean_object_state_labels.json`: final reviewed object-state labels with accidental SAM2 points removed.
- `annotations/manual_state_instance_manifest.json`: 276-scene instance manifest used by the annotation UI and modeling export.
- `annotations/manual_state_labels_seed.csv`: original 276-scene seed list.
- `annotations/cleaning_summary.json`: summary of removed points and label counts.
- `modeling/`: regenerated training/evaluation tables and baseline reports. Large generated crops/models are ignored by Git.

## Important Cleaning Note

All `sam2_prompts.positive_points` and `sam2_prompts.negative_points` were cleared. The current points were accidental UI clicks, not curated SAM2 prompts, so keeping them would hurt future SAM2 mask refinement.
