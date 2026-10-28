# P.CASH fork

Native camera library behind the P.CASH desktop QR scanner, consumed through
[piratecash/openpnp-capture-java](https://github.com/piratecash/openpnp-capture-java).
Based on Sparrow's `v0.0.30-2`.

- Tags: `v0.0.30-2-pcash.N`; the Java fork is tagged with the same name.
- A `v*` tag runs `.github/workflows/release-natives.yml`, which publishes a release with
  `openpnp-capture-{macos-arm64,linux-x64,windows-x64}.tar.gz` (each holds `<jna-platform>/<library>`)
  and `natives.sha256`. Pull requests build the same matrix without publishing.
- Source patches on top of upstream: release builds drop `-march=native`, and `Context::openStream`
  frees a stream that failed to open (with the Windows/Linux stream members initialised so that is safe).
