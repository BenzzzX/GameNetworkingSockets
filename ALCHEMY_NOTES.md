# Alchemy Integration Notes

This repository is vendored for the native transport backend migration path.

Current integration assumptions:

- `ALCHEMY_GNS_RUNTIME=ON` enables the transport-facing compile path in
  `alchemy_native`
- `ALCHEMY_GNS_VENDOR_READY=ON` additionally enables building the vendored
  `GameNetworkingSockets` static library through the top-level CMake project
- the current vendored build path enables native `ENABLE_ICE=ON` without
  pulling in the optional SteamWebRTC dependency chain
- TURN/STUN/signaling server components live under `deploy/networking/` and
  `services/net-directory/`

If you want to build the vendored GNS library on Windows, use
`scripts/bootstrap_gns_windows.cmd` first to provision `vcpkg` and protobuf.
