# Vinardock-exec

Prebuilt executables for **linux/amd64** (compiled on Ubuntu 24.04).

| Asset | Description |
|---|---|
| `vinardock-linux-amd64` | Vinardock molecular docking (Vinardo scoring, PSO-MC swarm). Requires `libstdc++`, `libgomp` (standard on Ubuntu/Debian).|
| `obabel-linux-amd64` | Open Babel `obabel`, statically linked. No dependencies beyond glibc + zlib. |
| `param/` | Vinardo parameter tables required by `vinardock` at runtime. Point the binary at them with `--scoring.table param/param.dat` and `--scoring.tableTxT param/param.TxT.dat`. |

## Download

```bash
# vinardock
curl -L -o vinardock https://github.com/arloa/Vinardock-exec/releases/latest/download/vinardock-linux-amd64
chmod +x vinardock

# obabel
curl -L -o obabel https://github.com/arloa/Vinardock-exec/releases/latest/download/obabel-linux-amd64
chmod +x obabel
```

## Verify integrity

```bash
curl -LO https://github.com/arloa/Vinardock-exec/releases/latest/download/sha256sums.txt
sha256sum --check sha256sums.txt --ignore-missing
```

Pinned to a specific version? Replace `latest` with the tag, e.g. `releases/download/v1.0.0/...`.
