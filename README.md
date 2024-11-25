# Regenerating generated-sources.yaml

Sometimes, we need to regenerate the `generated-sources.yaml` file manually, e.g. when upstream adds a new zip file the app needs.

To do that, invoke the helper Python script found in the `tools/sources-generator` directory:

```sh
# Initialize the git submodule in the 'tools' directory
git submodule update --init
# Create a virtual Python environment in the '.venv' directory
python3 -m venv .venv
# Activate the environment
source .venv/bin/activate
# Install the script dependencies
python3 -m pip install -Ur tools/sources-generator/requirements.txt
# Regenerate the sources file
./tools/sources-generator/generate.py -e 2023 > generated-sources.yaml
```

TThen, test the changes by rebuilding and running the app.
