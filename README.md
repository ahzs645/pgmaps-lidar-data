# PGMaps LiDAR data

Point-cloud tiles that [PGMaps](https://github.com/ahzs645/PGMaps) loads at runtime, published
here so they stay out of its GitHub Pages deployment. PGMaps pins this repository as a submodule
at `vendor/pgmaps-lidar-data`.

| Part | Where | Why |
| ---- | ----- | --- |
| Build | `prepare-lidar.py`, `environment.yml` | Builds EPT from one checksummed LAZ with Entwine |
| Storage | Release `bc-093g086-v1` | One archive, so a rebuild is never needed to redeploy |
| Serving | GitHub Pages | Pages sends CORS headers; release downloads do not |

The tiles are not in Git. To rebuild them, bump `RELEASE` in `.github/workflows/publish.yml`.

`LICENSE` covers the code here. The tiles derive from the source named in `prepare-lidar.py`.

To work with the tiles locally, for the offline checks in PGMaps' `scripts/lidar`:

    micromamba create -f environment.yml
    micromamba run -n pgmaps-lidar-data python prepare-lidar.py --output ../../public/data/lidar/bc-093g086
