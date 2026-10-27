# Orbiter 2027 Linux: planet and moon textures

Surface, mask, elevation and cloud tiles (TileFormat 2) for the planets and moons of
[Orbiter 2027 Linux](https://github.com/racerx2/orbiter-2027-linux).

The files are in the [releases](https://github.com/racerx2/Orbiter-linux-orbital-bodies-textures/releases):

- one zip per body and layer, `<Body>_<Layer>.zip`, about 1.4 GB together;
- Earth in high resolution: the `Surf`, `Mask`, `Elev`, `Elev_mod` and `Cloud` archives (`.tree`, 33 GB),
  cut into 1 GiB parts, `Earth_<Layer>.tree.NN`.

When a scenario is launched and textures are missing, Orbiter's Launchpad lists them and offers to
download and install them; a cut-off Earth download carries on where it stopped.

By hand: unzip a pack into the Orbiter folder, it adds `Textures/<Body>/<Layer>`; join an Earth
archive's parts into `Textures/Earth/Archive`, for example

    cat Earth_Surf.tree.* > Textures/Earth/Archive/Surf.tree

`md5.txt` has the checksums of the release files, `md5-archives.txt` those of the joined archives,
`CREDITS.txt` the map sources and licences.

## SPICE ephemeris kernels

The [kernels-1](https://github.com/racerx2/Orbiter-linux-orbital-bodies-textures/releases/tag/kernels-1) release holds the
SPICE kernels Orbiter places the planets and moons from (1900 to 2199); the Launchpad offers them when they are missing:

- `orbiter.bsp.01`, `orbiter.bsp.02`: upstream OpenOrbiter's merged kernel (JPL DE442, mar099, jup365, jup344, sat441,
  ura182, nep098, plu060, sb441-n16), 1,637,029,888 bytes, md5 b53fb18b32654ee90f54fb830cf838ed when joined;
- `kerberos_styx.bsp.01`: Kerberos and Styx, their segments of JPL's plu060 copied unchanged (Orbiter's Utils/SpiceSubset).

By hand: `cat orbiter.bsp.0* > Kernels/orbiter.bsp` and `cp kerberos_styx.bsp.01 Kernels/kerberos_styx.bsp` in the
Orbiter folder. `md5-kernels.txt` has the checksums of the release files. The kernels are JPL's (NASA), free to use.
