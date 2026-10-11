# KernelSU Modules

The module repository for [KernelSU](https://kernelsu.org): **https://modules.kernelsu.org**

Modules stay in their authors' own GitHub repositories. KernelSU Modules indexes their releases,
validates every ZIP and serves it to KernelSU Manager.

### Module Submission

https://developers.kernelsu.org

Sign in with GitHub, pick your repository and submit. A maintainer reviews a new module once;
after that every new release is picked up automatically.

### Repo Requirements

A valid repo should match the following requirements:

1. Public GitHub repository that you administer, with the [KernelSU Modules App](https://github.com/apps/kernelsu-modules) installed
1. `module.yaml` in the repository root with the module ID, name, summary and description document ([reference](https://developers.kernelsu.org/docs/module-yaml))
1. Release immutability enabled: **Settings → General → Releases → Enable release immutability**
1. A valid release is immutable and has exactly one module ZIP asset; `id`, `version` and `versionCode` are read from `module.prop` inside the ZIP, and `versionCode` must be higher than any previous release

### Best Practice to release

Push a tag and let [`KernelSU-Modules/tools/actions/module-release`](https://github.com/KernelSU-Modules/tools/tree/main/actions/module-release)
zip, check and publish the release. Start from [example-module](https://github.com/KernelSU-Modules/example-module).
Closed-source module? Keep the source private and publish to a public release repository, see
[example-closed-module](https://github.com/KernelSU-Modules/example-closed-module).

Validation results appear as the **KernelSU Modules** check on the tag commit and in the Developer Portal.

**Note that** an immutable release cannot be changed. To fix a release, publish a new one with a higher `versionCode`.

[Developer documentation](https://developers.kernelsu.org/docs/) · [中文文档](https://developers.kernelsu.org/docs/zh-CN/)
