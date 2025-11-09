# GitHub Actions: Multi-Platform Matrix Build Challenge

This repository demonstrates a multi-platform build strategy using a GitHub Actions matrix.

## Purpose

The goal is to fulfill a DevOps challenge that requires:
- A matrix build with at least 3 parallel jobs.
- Each job generating and uploading a unique, non-empty build artifact.
- Artifacts named with a specific prefix (`build-1b4daa7-<variant>`).
- A specific step identifier (`matrix-1b4daa7`) included in the workflow.

## Workflow Details

The CI/CD pipeline is defined in `.github/workflows/matrix-build.yml`.

- **Trigger**: The workflow runs on every `push` to the `main` or `master` branch and can also be triggered manually (`workflow_dispatch`).
- **Matrix Strategy**: It uses a Python version matrix for `['3.9', '3.10', '3.11']`. This creates three parallel jobs, one for each Python version.
- **Artifact Generation**: Each job creates a simple text file (`build-output.txt`) containing a message with the Python version used for the build.
- **Artifact Upload**: The `actions/upload-artifact@v4` action is used to upload the generated text file. The artifact is dynamically named `build-1b4daa7-py<python-version>` to be unique for each job.

After a successful run, you will find three artifacts available for download in the "Summary" section of the workflow run.

## Contact

For any questions, please contact: `23f2004076@ds.study.iitm.ac.in`
