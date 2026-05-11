# mv-refs — shared music-video reference image hosting

Stable, public CDN-style hosting for music-video character reference images, served via `raw.githubusercontent.com`.

## Structure

```
mv-refs/
├── <song-slug-kebab>/
│   ├── <character_id>.<ext>
│   └── ...
└── README.md
```

## URL pattern

```
https://raw.githubusercontent.com/galtpos/mv-refs/main/<song-slug-kebab>/<file>
```

## Auto-rehost

Maintained by `~/Documents/CTO/orchestrators/ref_health_orchestrator.py`. Runs as preflight in Phase C of the v2 music-video pipeline. When `references.json` URLs return non-200, the orchestrator copies the local file from the song project's `refs/` directory into the appropriate subdir here, commits, pushes, and patches `references.json` with the new raw URL.

Per `feedback_systems_must_self_correct_not_just_notify.md`.
