# strings_oc releases

## 1.0.8
- Switched to pyproject.toml with wheel generation
- `random()` now uses `secrets.randbelow` instead of `random.randint` so
  session / reset / internal keys are CSPRNG-backed.
- Fixed `to_bool` so non-string input raises `ValueError` instead of
  returning it, and the error message is formatted correctly.
- Fixed `to_file` so `create_path=False` no longer creates missing
  directories; path creation only happens when `create_path=True`.
- Added `cut` to `__all__` so it is exported with the rest of the public
  API.
- `shorten_filename` now raises `ValueError` when the requested length is
  too short to keep the extension and at least one name character,
  instead of returning an over-long or extension-only string.
- Fixed `normalize` so Cyrillic capital `А` maps to `A` instead of `a`.
- `cut` default ellipsis is now `…` instead of `...`.