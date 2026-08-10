# FPGA Based Scan Debug Replication Backup

Backup date: 2026-08-10

This folder keeps only the source files needed to replicate the FPGA-based scan-debug setup around `scan_debug_read_mode`.

## Contents

- `caravel_firmware/external_scan_setup.c`: Caravel firmware that configures scan-debug pins as external user inputs and analog rails as analog pads.
- `teensy_adc_dac_control/DAC_analog_vltgs.ino`: Teensy ADC/DAC control sketch used for DAC rail setting and ADS1258 current monitor reads.
- `teensy_adc_dac_control/DAC_read.h`: DAC channel mapping/helper header required by the ADC/DAC sketch.
- `teensy_adc_dac_control/DAC_voltage_setter_000FAF0B.ino`: Standalone DAC voltage setter sketch kept as a minimal DAC-control reference.
- `teensy_adc_dac_control/ADS1258_Simple/`: Local ADS1258 library source required by `DAC_analog_vltgs.ino`.
- `teensy_clk_control/teensy_si5351_clk1_2mhz.ino`: Si5351 clock Teensy sketch.
- `fpga_verilog/FPGA_SOURCE_NOT_FOUND.md`: FPGA source/readback status.
- `SHA256SUMS`: Checksums for the backed-up files.

## Not Included

The older `TEST_Bench` copy was moved out of `TEST_Bench`. GUI scripts, setup diagrams, plots, and broad experiment data were intentionally not included here because they are not required to rebuild the firmware/sketches.
