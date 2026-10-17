# Fork changes (Creator 5 Pro personal build)

Base: upstream OrcaSlicer tag `v2.4.2`. Integration branch `ff-main`; one feature per `ff/<name>` branch.
To move to a new upstream tag: `git fetch upstream --tags && git rebase --onto <new-tag> v2.4.2 ff-main`.

| Change | Files | Why |
|---|---|---|
| Windows x64 CI build | `.github/workflows/ff_build_windows.yml` (new) | Installer without a local compiler; separate file so upstream workflows stay untouched. |
