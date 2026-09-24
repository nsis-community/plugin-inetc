# build-plugin-inetc

Test fixture for [nsis-dev/build-plugin](https://github.com/nsis-dev/build-plugin).

> [!CAUTION]
> This is not an official plugin repository.

**Covers:** C++ with a dialog `.rc`, wininet, and `crt: none` with its own `crt.cpp` (memset and string functions). msvc only: `crt.cpp` conflicts with MinGW's C++ headers.

**Changed from upstream:** Dropped the bundled Plugin API copy (`pluginapi.c/.h`, `api.h`, `nsis_tchar.h`); `#include "pluginapi.h"` became `#include <nsis/pluginapi.h>`; `crt.cpp` uses the `__stosb` intrinsic only on x86 and x64, so arm64 builds.
