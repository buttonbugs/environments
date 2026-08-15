# Git Large File Storage (LFS)

## Install LFS

Run the following command globally on your system.

```bash
git lfs install
```

## Setup LFS

Run the same command again locally for the repository.

```bash
git lfs install
```

## How to Fix Already Tracked Files

```bash
git lfs migrate import --no-rewrite --include="*.[mM][pP]4"
```

Omit `--no-rewrite` if you want to alter your historical commits and purge the heavy video binaries completely from your repository history.