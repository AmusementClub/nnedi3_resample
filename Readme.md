# nnedi3_resample

## Requirements

- nnedi3 / znedi3
- fmtconv
- mvsfunc

## Usage

Put nnedi3_resample.py into `<python folder>\Lib\site-packages\vapoursynth`

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

1. Add new option `mode`, default value is nnedi3, you can use `mode=znedi3` to instead it, znedi3 may be faster than nnedi3.
2. Chage how to import core because `get_core` is deprecated.
3. Remove `YCOCG` and `COMPAT`, this will be deprecated in API4.
