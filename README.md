# Vinardock-exec

Prebuilt executables for **linux/amd64**.

| Asset | Description |
|---|---|
| `vinardock-linux-amd64` | Vinardock molecular docking (Vinardo scoring, PSO-MC swarm), compiled on Ubuntu 24.04. Requires `libstdc++`, `libgomp` (standard on Ubuntu/Debian).|
| `vinardock-linux-amd64-ubuntu22.04` | Same binary compiled on Ubuntu 22.04 — use this on systems with glibc < 2.39. |
| `obabel-vinardock-linux-amd64` | Open Babel `obabel`, statically linked. No dependencies beyond glibc + zlib. |
| `obabel-vinardock-linux-amd64-ubuntu22.04` | Open Babel `obabel` built on Ubuntu 22.04, dynamically linked — requires `libopenbabel.so.7` and Open Babel 3.1.1 plugins installed. |
| `param/` | Vinardo parameter tables required by `vinardock` at runtime. Point the binary at them with `--scoring.table param/param.dat` and `--scoring.tableTxT param/param.TxT.dat`. `param/dun2010bbdep.bin` is the Dunbrack 2010 backbone-dependent rotamer library, needed for flexible-residue/design runs via `--rotamer_lib param/dun2010bbdep.bin`. |

## Download

```bash
# vinardock (Ubuntu 24.04+)
curl -L -o vinardock https://github.com/arloa/Vinardock-exec/releases/latest/download/vinardock-linux-amd64
chmod +x vinardock

# vinardock (Ubuntu 22.04 build)
curl -L -o vinardock https://github.com/arloa/Vinardock-exec/releases/latest/download/vinardock-linux-amd64-ubuntu22.04
chmod +x vinardock

# obabel-vinardock
curl -L -o obabel-vinardock https://github.com/arloa/Vinardock-exec/releases/latest/download/obabel-vinardock-linux-amd64
chmod +x obabel-vinardock

# obabel-vinardock (Ubuntu 22.04 build)
curl -L -o obabel-vinardock https://github.com/arloa/Vinardock-exec/releases/latest/download/obabel-vinardock-linux-amd64-ubuntu22.04
chmod +x obabel-vinardock
```

## Verify integrity

```bash
curl -LO https://github.com/arloa/Vinardock-exec/releases/latest/download/sha256sums.txt
sha256sum --check sha256sums.txt --ignore-missing
```

Pinned to a specific version? Replace `latest` with the tag, e.g. `releases/download/v1.0.0/...`.
