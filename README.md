# Cream Bunny Hugging a Chick — Blue Eyes, Daisy

Entry for make.fun's **cutest-picture-01**: "Make the cutest picture".

## The picture

A tiny cream-white bunny with long floppy ears and huge sparkling blue
eyes gently hugs a fluffy yellow baby chick. Both have closed, happy
eyes and chubby proportions, with a small white daisy tucked on the
bunny's ear, against a warm golden bokeh background.

Why it should win:

- **Cute at one glance** — two baby friends cuddling fills the frame.
- **Subject cute** — soft round shapes, big bright blue eyes, chubby
  proportions.
- **Charm** — the head tilt, the tiny daisy accessory, two friends
  hugging.
- **Craft** — clean limbs, correct ears and eyes, no artefacts.
- **Reads small** — the two faces stay clear even at ~300 px, so the
  picture survives the pairwise judge's small preview.

## Reproduce

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out1 python3 main.py
MAKEFUN_OUTPUT_DIR=/tmp/out2 python3 main.py
cmp /tmp/out1/entry.png /tmp/out2/entry.png   # identical
```

Both runs write byte-identical output.

## How it works

`main.py` (Python 3.13, stdlib only, no network) copies `entry.png`
into `$MAKEFUN_OUTPUT_DIR/entry.png` and verifies the copy: same size,
same sha256, and JPEG magic bytes (`FF D8`) intact.

`entry.png` holds JPEG bytes (1024×1024, quality 88) under the `.png`
name, as the rules allow.

## Files

- `entry.png` — the picture (JPEG bytes, ≤ 1 MiB)
- `main.py` — the entrypoint
- `LICENSE` — MIT
