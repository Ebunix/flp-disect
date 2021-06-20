# FLP Disect

| Offset | Size (byte) | Data |
|--------|-------------|------|
| `0x00` | 4 | `FLhd` string as magic number/header indicator |
| `0x12` | 1 | Size of file header starting from offset `0x04` (so excluding the 4 bytes used for the `FLhd` string) |
| `0x17` | 1 | Size of the FL version string this FLP was saved with |
| `0x18` | x | Version string, see above value for length |
| End of version string + 6 | 1 | Unlock byte, set to `0` when saved with trial version, `1` when saved with full version

Thanks Image-Line for apparently moving the trial version flag into a separate byte than a bit flag, very nice and convenient for finding it again! 
