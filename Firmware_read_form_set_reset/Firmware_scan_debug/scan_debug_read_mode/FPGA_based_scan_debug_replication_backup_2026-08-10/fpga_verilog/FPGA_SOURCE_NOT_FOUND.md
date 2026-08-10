# FPGA Source Status

No FPGA Verilog, XDC, Vivado Tcl, bitstream, or debug probe file was present locally in this repository at backup time.

Checked local paths:

- `fpga_scan_debug_zynq7020/` existed but was empty.
- Searches under `/Users/samarthjain/Documents/GitHub` found no `caravel_scan_debug_fpga.v`, scan-debug `.xdc`, Zynq Tcl, `.bit`, or `.ltx` files.

Checked remote access:

- SSH to `geethika@100.116.216.70` reached a Windows host.
- A recursive search under `C:\Users\geethika` for the expected FPGA source/bitstream names returned no matches.

Readback note:

- The local machine does not have `vivado` or `openFPGALoader` available.
- Even with JTAG readback, the original Verilog source cannot be reconstructed from a programmed FPGA. At best, a configuration bitstream/readback image may be recoverable if Vivado hardware tools can connect to the board.
