# Alternative architectures

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

As stated in the [Prerequisites](prerequisites.md), currently only `amd64` (`x86_64`) is fully supported.

The playbook automatically determines the target server's architecture (the `matrix_architecture` variable) to be one of the following:

- `amd64` (`x86_64`)
- `arm32`
- `arm64`

Some tools and container images can be built on the host or other measures can be used to install on that architecture.

## Implementation details

For `amd64`, prebuilt container images (see the [container images we use](container-images.md)) are used for all components (except [Hydrogen](configuring-playbook-client-hydrogen.md), which goes through self-building).

For other architecture (`arm64`, `arm32`), components which have a prebuilt image make use of it. If the component is not available for the specific architecture, [self-building](self-building.md) will be used. Not all components support self-building though, so your mileage may vary.
