# Raw Data

The raw SynthSoM-Twin data is organized by complete scenario names and distributed through the permanent Baidu Netdisk links in [dataset/README.md](../README.md).

- [Suburban daytime](suburban_daytime/README.md)
- [Urban daytime](urban_daytime/README.md)
- [Urban nighttime](urban_nighttime/README.md)

Each scene uses the following directory layout:

~~~text
raw/
├── suburban_daytime/
├── urban_daytime/
└── urban_nighttime/
~~~

Every scene directory contains the common package locations `communication/mmwave_60ghz/`, `sensing/rsu/`, `sensing/vehicle/`, and `real_world/`. Scene-specific package coverage is described by the files placed in the corresponding Netdisk directory.
