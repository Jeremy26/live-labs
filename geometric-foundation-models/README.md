# Live Lab 2 · 3D Reconstruction: COLMAP vs Geometric Foundation Models

Notebook: `Lab2_3D_Reconstruction.ipynb` (about 10 minutes, no code to write).

| Session | Content |
|---|---|
| **1 · Your SfM vs COLMAP** | Your Lab 1 SfM on the fountain, what breaks, then the 3 bricks COLMAP adds (tracks, PnP, bundle adjustment), then the real COLMAP |
| **2 · Depth Anything 3** | A geometric foundation model on the same photos, one forward pass |
| **3 · Our photos** | COLMAP vs Depth Anything 3 on your own photos, 4 numbers each, then a trap round |

## How to run

1. Open the notebook in Google Colab (replace the branch name if it changed):
   `https://colab.research.google.com/github/Jeremy26/live-labs/blob/claude/nice-pascal-rm48io/geometric-foundation-models/Lab2_3D_Reconstruction.ipynb`
2. **Runtime > Change runtime type > T4 GPU.**
3. Run the cells from top to bottom. The first cell (Setup) takes 1 to 2 minutes.
4. In Session 3, upload a `.zip` of 10 to 20 JPEG/PNG photos (or the photos directly).
   Nothing uploaded: the fountain is used.

## Photos for Session 3
- One textured scene, move around it (do not spin in place).
- Photos are shrunk to 1600 px on the long side to keep COLMAP fast.
- Trap round: a set made to fail (spinning in place, a white wall, or only 3 photos).

## Good to know
- The red/yellow messages about `gsplat`, `HF_TOKEN` or `SyntaxWarning` are harmless.
- Without a GPU the notebook still runs, but Depth Anything 3 is slow.
- Session 1 follows Lab 1 (`SFM_Run`): same fountain photos, same camera matrix.
  One change: the essential matrix comes from `cv2.findEssentialMat` instead of `K.T @ F @ K`
  (the reprojection error of a pair goes from 5.9 px to 0.1 px).
