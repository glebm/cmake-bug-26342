# Pretend that this is a third-party library that also uses SDL2
#
# We want this to succeed regardless of how the top-level project
# obtained SDL2.
find_package(SDL2 REQUIRED

  # We use NO_DEFAULT_PATH for the purposes of bug repro
  # (to simulate the case where SDL2 is not installed on the system)
  NO_DEFAULT_PATH
)
