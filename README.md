# SDL3-CS

C# bindings for the [SDL3](https://github.com/libsdl-org/SDL) family of libraries.

| Product                                                          | Usage                                  | Package                                                                                                                    |
|------------------------------------------------------------------|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| [`SDL`](https://github.com/libsdl-org/SDL/tree/main)             | `dotnet add package Ryujinx.SDL3-CS`       | [![NuGet](https://img.shields.io/nuget/v/Ryujinx.SDL3-CS?label=nuget)](https://www.nuget.org/packages/Ryujinx.SDL3-CS)             |

Contributions to keep the bindings up-to-date with upstream changes are welcome. If you have improvements or updates, feel free to submit a pull request.

## Platform support

| Product         | `win-x64` | `win-arm64` | `osx-arm64` | `osx-x64` | `linux-x64` | `linux-arm64` | `ios`   | `android` |
|-----------------|-----------|-------------|-------------|-----------|-------------|---------------|---------|-----------|
| `SDL3-CS`       | &check;   | &check;     | &check;     | &check;   | &check;     | &check;       | &check; | &check;   |

## How to update SDL

1. Ensure all submodules are correctly initialised:
   ```sh
   git submodule update --init --recursive
   ```
2. Check out submodules at new desired upstream commits.
3. Regenerate C# bindings via:
   ```sh
   docker build -t 'sdl-gen' .
   docker run --rm -v .:/app -w /app -it sdl-gen
   ```
4. Run the "Build Native" (`.github/workflows/build.yml`) workflow to generate platform binaries.

## License

This code is released under [MIT](LICENCE).
