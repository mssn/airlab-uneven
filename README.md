# BeyondFlat Dataset
**Note:** So far, only sample images are provided as supplementary materials to the submission under review. The full dataset will be released upon publication. 

BeyondFlat contains real-world image sequences and associated metadata collected over different terrain profiles and acquisition settings for low-altitude UAV research.

## Folder structure

Data is organized by **terrain type**, then by **data acquisition setting**. Depending on the released subset, terrain folders may include `flat`, `uphill`, `downhill`, and `composite` (or similarly named folders). Example acquisition-setting folders include:

```text
BeyondFlat/
├── composite/
│   ├── U-shape/
│   		├── ATO_2m/
│   		│	├── run_01/
│   		│	└── run_02/
│   		├── AGL_2m/
│   		└── AGL_3m/
├── uniform/
│	├── uphill/
│	└── downhill/
└── flat/
```

This tree illustrates the naming convention; not every terrain category necessarily contains every setting.

- **ATO_2m:** ATO recordings with the nominal setting indicated by the folder name (2 m or 3 m).
- **AGL_2m:** AGL recordings collected using a tripod-based setup, with a nominal 2 m setting.
- **AGL_3m:** AGL recordings collected using a vehicle-based setup, with a nominal 3 m setting.

Each recording contains image frames/video and a corresponding metadata text file. Frame order in the metadata matches the associated image sequence.
## Metadata format

Metadata files are plain-text (`.txt`) files, with **one row per image frame** and **five whitespace-separated columns**, in this order:

| Column | Field | Description |
| --- | --- | --- |
| 1 | Timestamp | Image capture time, expressed as a Unix timestamp in milliseconds. |
| 2 | Pitch | Recorded pitch value. |
| 3 | Altitude | Recorded drone altitude for applicable UAV recordings. **For AGL settings, this field is not meaningful and is set to `0.0` as a placeholder.** |
| 4 | Longitude | GPS longitude in decimal degrees. |
| 5 | Latitude | GPS latitude in decimal degrees. |

Example:

```text
1791494485926 0.0 0.0 -86.89944581295087 40.436292972847184
1791494487458 0.0 0.0 -86.89943515919602 40.4363909622887
1791494489118 0.0 0.0 -86.89941831604841 40.43651890478154
```


