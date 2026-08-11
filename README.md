# PSZ Test Repository

This is a simple demo / test project for the **[PSZ](https://github.com/SlabyLol/psz)** encrypted archive tool.

## What this repo does

- Contains a small sample project in the `sample-project/` folder
- Has a GitHub Actions workflow that:
  1. Installs PSZ
  2. Packs `sample-project/` into an encrypted `.psz` + matching `.psz-data.lor`
  3. Uploads both files as artifacts

## How to test locally

```bash
# Install PSZ
pip install git+https://github.com/SlabyLol/psz.git

# Create archive from the sample project
psz make sample-project -o demo.psz

# Extract it again
psz open demo.psz demo.psz-data.lor -o extracted/

# Or run the generated loader directly
python demo.psz-data.lor demo.psz -o extracted/
```

## Trigger the test workflow

- Go to the **Actions** tab of this repository
- Run the workflow "Build and create PSZ archive" manually, or just push a change

After the workflow finishes you can download the artifacts:
- `demo.psz`
- `demo.psz-data.lor`

---

Main tool: https://github.com/SlabyLol/psz
