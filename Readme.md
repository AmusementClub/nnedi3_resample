# nnedi3_resample

**You should better use https://github.com/HomeOfVapourSynthEvolution/nnedi3_resample**

## Requirements

- [nnedi3](https://github.com/dubhater/vapoursynth-nnedi3) / [znedi3](https://github.com/sekrit-twc/znedi3) / [nnedi3cl](https://github.com/HomeOfVapourSynthEvolution/VapourSynth-NNEDI3CL)
- [fmtconv](https://github.com/EleonoreMizo/fmtconv)
- [mvsfunc](https://github.com/AmusementClub/mvsfunc)

## Usage

Put nnedi3_resample.py into `<python folder>\Lib\site-packages\vapoursynth` or `<python folder>\Lib\site-packages`

## Function

It can do scaling, color space conversion, etc.

**Note**: Internally always processing in 16-bit integer, and the output format can be specified by "csp" with Format id (default is the same as input).

## Example

Double the width and height of a clip.

```python
import vapoursynth as vs
from vapoursynth import core
import nnedi3_resample as nnrs

clip = XXXSource()
clip = nnrs.nnedi3_resample(clip, clip.width * 2, clip.height * 2, mode='znedi3')

clip.set_output()
```

## ChangeLog

1. Add new option `mode`, default value is `nnedi3`, optional value:
    - `znedi3`, it may be faster than nnedi3
    - `nnedi3cl`, it can be used with new options `device` (same as the parameter of the plugin with the same name)
2. Chage how to import core because `get_core` is deprecated.
3. Remove `YCOCG` and `COMPAT`, these will be deprecated in API4.
4. Use fmtconv to convert gamma and linear.
