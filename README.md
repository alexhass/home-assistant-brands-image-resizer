# Home Assistant Brand Images Generator

This script generates PNG logos and icons suitable for Home Assistant integrations according to the [brands repository](https://github.com/home-assistant/brands) guidelines. No need to learn all the many rules or a image software you never heard about with uncountable many settings you have no clue about. Run and forget.

## Requirements

- Python 3.7 or newer
- Pillow library (for image processing)

Install the dependency:

```bash
pip install Pillow
```

## Usage

Run the script from the repository root (recommended) or from the `scripts` folder. Provide the source image path and the target directory where the generated images should be written.

POSIX example:

```bash
python scripts/brands_image_resizer.py docs/assets/brand/example.png custom_integrations/DOMAIN
```

Windows (PowerShell) example:

```powershell
python .\scripts\brands_image_resizer.py .\scripts\example.png ..\custom_integrations\DOMAIN
```

Notes:

- `source` can be any existing image file; PNG is recommended.
- `target_dir` will be created with `parents=True` if missing.

## Output files

By default the script generates the following files in the `target_dir`:

- `icon.png` (256×256)
- `icon@2x.png` (512×512)
- `logo.png` (256×128)
- `logo@2x.png` (512×256)
- `dark_icon.png` (256×256)
- `dark_icon@2x.png` (512×512)
- `dark_icon.png` (256×128)
- `dark_icon@2x.png` (512×256)

These sizes and filenames are defined in the `FILES` list inside `scripts/brands_image_resizer.py` and can be adjusted there if you need different sizes.

## Troubleshooting

- If you see `Source image not found`, verify the `source` path you passed is correct and readable.
- If Pillow import fails, ensure you installed it into the same Python environment you use to run the script.
- To inspect or change the sizes/filenames edit the `FILES` array inside `scripts/brands_image_resizer.py`.

---

For details on required image conventions, see the [brands repository](https://github.com/home-assistant/brands).

## License

MIT License - see LICENSE file
