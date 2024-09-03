# mkchd

_chdman made easy_

```
Usage: mkchd CUE_FILE
   or: mkchd CHD_FILE
```

Converts a CD to CHD format compressed with zstd + FLAC.
The hunk size is also reduced from 8 to 4 sectors, which is required
to decompress quickly enough for x8 CD speed on MiSTer FPGA.
The input file(s) will be removed (if BIN/CUE) or replaced (if CHD).

[chdman](https://docs.mamedev.org/tools/chdman.html) v0.262 or higher must be
in your PATH.

## Environment variables

* `TMPDIR`: directory for temporary files (default: `/tmp`)

## Examples

Compress a bin/cue disc:
```bash
mkchd "/path/to/Disc.cue"
```

Recompress a CHD:
```bash
mkchd "/path/to/Disc.chd"
```

Convert all discs in the current directory:
```bash
for file in *.cue; do ${script_name} "\${file}"; done
```

Convert all discs in the current directory and subdirectories:
```bash
find . -name '*.cue' -execdir ${script_name} '{}' ';'
```
