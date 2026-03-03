Model: Temporal Convolutional Network (TCN) on fixed-length ECG windows for complex arrythmia detection under embedded compute constraints (notes below before inspecting code)


Data: MIT-BIH Arrhythmia DB, AFDB, LTAFDB (record-wise handling)

Labels: Window-level, derived from clinical annotations

Results on FAST_DEV_RUN. AF: recall ≈ 95%, F1 ≈ 0.67, AP ≈ 0.99 Brady / Pause: high sensitivity, low precision (exploratory heads)

AF detection shows strong separability; threshold controls precision/recall trade-off

Brady/Pause are rare and temporally diffuse; window-level predictions benefit from post-processing (e.g., smoothing)

FAST_DEV_RUN uses a small, representative record subset for rapid iteration; full runs aggregate all records

Window-level predictions are noisy; temporal smoothing or episode-level aggregation would likely improve precision.
