# Clear Data Training Report

## Cleaning Summary

- Scenes: 276
- Instances: 600
- Non-unknown labeled instances: 521
- Bad/unreliable polygon instances: 62
- Cleared SAM2 positive points: 5
- Cleared SAM2 negative points: 718

## Export Summary

- Train candidate scenes: 258
- Validation holdout scenes: 18
- Train examples used by classifier: 339
- Validation examples: 65
- Test examples: 76

## Learned Crop Classifier Results

| Mode | Category | Val Acc | Val Bal Acc | Test Acc | Test Bal Acc | Test Examples |
|---|---:|---:|---:|---:|---:|---:|
| RGB | door | 0.708 | 0.562 | 0.556 | 0.500 | 18 |
| RGB | lamp | 0.850 | 0.885 | 0.885 | 0.727 | 26 |
| RGB | monitor_or_tv | 0.857 | 0.639 | 0.781 | 0.781 | 32 |
| RGBD | door | 0.625 | 0.469 | 0.667 | 0.625 | 18 |
| RGBD | lamp | 0.850 | 0.885 | 0.846 | 0.807 | 26 |
| RGBD | monitor_or_tv | 0.857 | 0.639 | 0.750 | 0.750 | 32 |

## Short Interpretation

- Lamp state is the most learnable target after cleaning, likely because on/off often has direct visual brightness cues.
- Monitor/TV improves substantially on the clean split, especially RGB, because screen on/off is often visible from color/brightness.
- Door remains difficult. RGB-D helps door test balanced accuracy, but open doors are still often missed because open/closed depends on viewpoint, occlusion, and geometry.
- SAM2 points were removed intentionally. Future SAM2 prompts should be curated manually or regenerated, not inherited from accidental drag/click interactions.
