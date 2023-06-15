# Droidian Installer configs ![Continuous Integration](https://github.com/droidian-devices/installer-configs/workflows/Continuous%20Integration/badge.svg)

This repository contains the config files for [Droidian Installer](https://github.com/droidian-releng/droidian-installer) devices.

Devices are configured using [YAML](https://yaml.org/) files following the [schema specifcation](./v2/schema/_.schema.yml) in the [./v2/devices](./v2/devices) directory.

If you want to propose changes to the structure or propose a new action, open an [issue](https://github.com/ubports/installer-configs/issues/new). Device-specific installation issues should be filed directly against the [Droidian Installer's repository](https://github.com/droidian-releng/droidian-installer/issues/new).

## Contributing

If you want to add a or improve a device, run `npm run build && npm run validate` to make sure your file follows the specification and `npm run lint` to make it pretty. You can use `npm run checksemver` to validate semver strings and `npm run checkdownloads` to make sure all files download successfully. If you modify any specifications, use `npm run test` to run specification validation tests.

You can use your local config file with the [Droidian Installer](https://github.com/droidian-releng/droidian-installer) by supplying the `--file` or `-f` flag:

```
droidian-installer -f ./path/to/config.yml
```

## Library usage

Install using `npm i droidian-installer-configs`.

```javascript
import validate from "droidian-installer-configs";

validate(object); // will return true or false
```

TypeScript Types for the config file schema are exported as `UBportsInstallerConfig`.

```typescript
import { validate, UBportsInstallerConfig } from "droidian-installer-configs";

validate(object as UBportsInstallerConfig);
```

## License

Original development by [Johannah Sprinz](https://spri.nz). Copyright (C) 2019-2022 [UBports Foundation](https://ubports.com). Copyright (C) 2023 Erik Inkinen <erik.inkinen@erikinkinen.fi>

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.
