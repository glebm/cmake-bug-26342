# We want to use SDL2 system package if installed,
# otherwise `FetchContent`.
# In both cases, we want all subsequent calls to
# `FindPackage` to be no-op.
FetchContent_Declare(SDL2
  URL https://github.com/libsdl-org/SDL/archive/refs/tags/release-2.30.7.tar.gz
  URL_HASH MD5=ace1a2fcfd1001690471f2e9a04b3ddc
  EXCLUDE_FROM_ALL

  # Ideally, we'd be able to specify this to ensure that
  # `find_package` calls are no-op even if FetchContent fallback was triggered.
  #
  # OVERRIDE_FIND_PACKAGE

  FIND_PACKAGE_ARGS

  # We use NO_DEFAULT_PATH for the purposes of bug repro
  # to trigger FetchContent fallback to fetching.
  NO_DEFAULT_PATH

  GLOBAL)
FetchContent_MakeAvailable(SDL2)
