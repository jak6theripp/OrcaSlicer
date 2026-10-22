# Fork changes (Creator 5 Pro personal build)

Base: upstream OrcaSlicer tag `v2.4.2`. Integration branch `ff-main`; one feature per `ff/<name>` branch.
To move to a new upstream tag: `git fetch upstream --tags && git rebase --onto <new-tag> v2.4.2 ff-main`.

| Change | Files | Why |
|---|---|---|
| Windows x64 CI build | `.github/workflows/ff_build_windows.yml` (new) | Installer without a local compiler; separate file so upstream workflows stay untouched. |
| Keep all 3MF settings (pref `ff_keep_3mf_settings`, default on; Preferences > "Keep all settings saved in 3MF files") | `Preset.cpp/.hpp` (`load_external_preset` `rebase_on_system`), `PresetBundle.cpp/.hpp`, `Plater.cpp`, `AppConfig.cpp`, `Preferences.cpp` | Stock Orca resets every key not in `different_settings_to_system` to the same-named installed system preset. Flash Studio's presets share names with Orca's Flashforge presets but not values, so its projects lost tower, filament and toolchange settings in the GUI. Flash Studio files carry no distinguishing metadata, hence a preference rather than detection. |
