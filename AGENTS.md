# PGMaps LiDAR data

- Keep tiles out of Git. The Release holds them and Pages serves them. Browsers cannot read a Release asset directly: GitHub sends no CORS headers on those downloads.
- This Pages site has its own 1 GB limit. Add datasets with that in mind.
- A Pages deployment is keyed by commit, and a cancelled commit cannot deploy again. Retry with a new commit, not a rerun.
- `prepare-lidar.py` refuses a source whose size or checksum has changed. Keep that check.
