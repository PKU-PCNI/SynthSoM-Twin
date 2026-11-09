# Dataset

The SynthSoM-Twin dataset is distributed through the permanent Baidu Netdisk directory links below. The three scene directories use the same descriptive naming convention as the repository.

## Download Locations

| Scenario | Baidu Netdisk directory | Extraction code | Validity |
|---|---|---|---|
| `suburban_daytime` (SC31) | [Open directory](https://pan.baidu.com/s/1C4c9BRjU3hqhsZ5S3ey_3g) | `e6qa` | Permanent |
| `urban_daytime` (SC32) | [Open directory](https://pan.baidu.com/s/11LJs57TgqvGYkwLF88ZQVw) | `pew6` | Permanent |
| `urban_nighttime` (SC33) | [Open directory](https://pan.baidu.com/s/1wGR4QxGfyCCPRupGFwkbnQ) | `e0tu` | Permanent |

The Baidu Netdisk release root is `/SynthSoM-Twin/dataset/raw/`. Each scene link corresponds to `dataset/raw/<scenario>/` in this repository. Use the extraction code shown in the table when accessing a shared directory.

## Dataset Organization

~~~text
dataset/
├── metadata/       # Dataset description, scenario metadata, and file manifests
├── raw/            # Original data organized by complete scenario names
│   ├── suburban_daytime/
│   ├── urban_daytime/
│   └── urban_nighttime/
├── processed/      # Data processed for inference
│   ├── suburban_daytime/
│   ├── urban_daytime/
│   └── urban_nighttime/
├── splits/         # Reproducible input and test split definitions
└── samples/        # Small examples for checking the code pipeline
    ├── example_path_loss/
    ├── example_beam_power/
    └── example_beam_tracking/
~~~

Each raw scene follows this layout:

~~~text
<scenario>/
├── communication/
│   └── mmwave_60ghz/
├── sensing/
│   ├── rsu/
│   └── vehicle/
└── real_world/
~~~

## Scenario Definitions

- **suburban_daytime (SC31)**: A suburban V2I setting on a straight two-lane road on the south edge of Arizona State University, with sparse buildings, low vegetation, and few vehicles and pedestrians.
- **urban_daytime (SC32)**: An urban V2I setting at the College Ave–5th St intersection in downtown Tempe, with tall buildings, dense trees, and substantial vehicle and pedestrian activity.
- **urban_nighttime (SC33)**: The same urban intersection as SC32 under nighttime visual conditions.

These names follow the scenario descriptions used in the paper: suburban, urban daytime, and urban nighttime V2I scenario settings.

## Usage

Configure the inference scripts under `code/inference/` with the local dataset path. Place each downloaded scene under the corresponding `dataset/raw/<scenario>/` directory.

## Data Management

Do not commit large raw data, generated predictions, checkpoints, or temporary files to GitHub. Preserve the scene names, package names, frame indices, sensor associations, and transmitter/receiver correspondence when copying or processing the dataset.
