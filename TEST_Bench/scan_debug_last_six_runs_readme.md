# Last Six FPGA Scan-Debug Runs

This file summarizes the last six FPGA-driven scan-debug experiments in reverse order, starting with the sixth-last run and ending with the latest run. The FPGA drives scan-debug control/data on the falling edge of `wb_clk_i`; Caravel samples on the rising edge. Current is computed from the Saleae analog shunt probes using a 1 kohm shunt:

`I = (V_plus - V_minus) / 1000 ohm`

Common DAC setup unless otherwise noted:

| Rail | Voltage |
|---|---:|
| `Vcc_read` | 0 V |
| `Vcc_reset` | 0 V |
| `Vcc_wl_read` | 0 V |
| `Vcc_wl_set` | 2.5 V |
| `Vcc_wl_reset` | 0 V |

Saleae channels used for this set:

| Signal | LA channel |
|---|---:|
| `ready` | 6 |
| `reset` / `rst_b` | 7 |
| `clk` | 8 |
| `TM` | 9 |
| `ScanInDL` | 10 |
| `ScanInDR` | 11 |
| Set shunt | 12 and 13 |
| Reset shunt | 14 and 15 |

## Run Index

| Reverse order | Capture time | Packet | `Vcc_set` | Decoded word | 16th bit | Set current, zoom mean | Reset current, zoom mean | Plot |
|---:|---|---:|---:|---:|---:|---:|---:|---|
| 6th last | 2026-08-11 12:28:28 | `0x0000` | 2.5 V | `0x0000` | 0 | 336.92 uA | 12.32 uA | [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_122828_fast_saleae_vccset2v5_setshunt_reconnected_currents_same_timescale.png) |
| 5th last | 2026-08-11 12:38:39 | `0x8000` | 2.5 V | `0x8000` | 1 | 403.33 uA | 652.62 uA | [PNG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_123839_fast_saleae_j10_7_dl_oneclk_vccset2v5_rerun_currents_same_timescale.png) |
| 4th last | 2026-08-11 12:51:04 | `0x0000` | 2.5 V | `0x0000` | 0 | 330.12 uA | 753.58 uA | [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_125104_fast_saleae_vccset2v5_rerun_currents_same_timescale.png) |
| 3rd last | 2026-08-11 16:13:57 | `0x0000` | 1.7 V | `0x0000` | 0 | -235.20 uA | 1.98 uA | [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_161357_fast_saleae_vccset1v7_rerun_currents_same_timescale.png) |
| 2nd last | 2026-08-11 16:31:07 | `0x8000` | 2.5 V | `0x8000` | 1 | -95.47 uA | 4.03 uA | [PNG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_163107_fast_saleae_vccset2v5_rerun_currents_same_timescale.png) |
| Last | 2026-08-11 16:39:42 | `0x0000` | 1.7 V | `0x0000` | 0 | -87.08 uA | 135.30 uA | [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_163942_fast_saleae_vccset1v7_rerun_currents_same_timescale.png) |

The zoom current values are measured on the same Saleae time scale as the timing diagram. ADC values are full-run context values because the ADC sampling did not necessarily land inside the microsecond scan-debug zoom window.

## 1. Sixth Last Run: `0x0000`, `Vcc_set = 2.5 V`, Set Shunt Reconnected

![Sixth last run timing and currents, PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_122828_fast_saleae_vccset2v5_setshunt_reconnected_currents_same_timescale.png)

![Sixth last run timing and currents, SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_122828_fast_saleae_vccset2v5_setshunt_reconnected_currents_same_timescale.svg)

Artifacts: [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_122828_fast_saleae_vccset2v5_setshunt_reconnected_currents_same_timescale.png), [SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_122828_fast_saleae_vccset2v5_setshunt_reconnected_currents_same_timescale.svg)

| Item | Value |
|---|---|
| Capture directory | `scan_debug_req0000_2026-08-11/capture_122828_fpga_manual_reset_fast_saleae_vccset2v5_setshunt_reconnected` |
| Bitstream SHA | `2A90436FBCD3590ACD0A945226791213E16EFC1CE921182F58EBD7AFE62330C7` |
| Rail command result | `vcc_read_mV=0 vcc_set_mV=2500 vcc_reset_mV=0 vcc_wl_read_mV=0 vcc_wl_set_mV=2500 vcc_wl_reset_mV=0` |

| Timing / decode | Value |
|---|---:|
| `ready` fall | 0.37884864 s |
| `ready` rise | 0.39032320 s |
| `TM` rise | 0.39038832 s |
| `ScanInDR` fall | 0.39038896 s |
| `ScanInDR` rise | 0.39039792 s |
| `ScanInDL` edges near packet | 0 |
| `TM` to `ScanInDR` fall | 0.64 us, 1.33 clk |
| `ScanInDR` low width | 8.96 us, 18.67 clk |
| Active rising edges while `ScanInDR` low | 18 |
| Decoded word | `0x0000` |
| LSB-first data bits | `0000000000000000` |
| 16th data bit | 0 |
| Extra active sample | 0 |

| Current source | Mean | Min | Max | Span | Samples |
|---|---:|---:|---:|---:|---:|
| Saleae set shunt, full run | 228.63 uA | -20.00 uA | 518.00 uA | 538.00 uA | 1265626 |
| Saleae reset shunt, full run | 0.79 uA | -36.00 uA | 93.00 uA | 129.00 uA | 1265626 |
| Saleae set shunt, zoom | 336.92 uA | -9.00 uA | 460.00 uA | 469.00 uA | 40 |
| Saleae reset shunt, zoom | 12.32 uA | 0.00 uA | 22.00 uA | 22.00 uA | 40 |
| ADC read, full run | 1144.30 uA |  |  |  | 27 |
| ADC set, full run | -24.84 uA |  |  |  | 27 |
| ADC reset, full run | -17.52 uA |  |  |  | 27 |

## 2. Fifth Last Run: `0x8000`, `Vcc_set = 2.5 V`

![Fifth last run timing and currents, PNG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_123839_fast_saleae_j10_7_dl_oneclk_vccset2v5_rerun_currents_same_timescale.png)

![Fifth last run timing and currents, SVG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_123839_fast_saleae_j10_7_dl_oneclk_vccset2v5_rerun_currents_same_timescale.svg)

Artifacts: [PNG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_123839_fast_saleae_j10_7_dl_oneclk_vccset2v5_rerun_currents_same_timescale.png), [SVG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_123839_fast_saleae_j10_7_dl_oneclk_vccset2v5_rerun_currents_same_timescale.svg)

| Item | Value |
|---|---|
| Capture directory | `scan_debug_req8000_2026-08-11/capture_123839_fpga_manual_reset_fast_saleae_j10_7_dl_oneclk_vccset2v5_rerun` |
| Bitstream SHA | `2DFF5EFF39D5AE864705B044AC4369AFAF7A269F69EFDA30DD3B1A060B20CA98` |
| Rail command result | `vcc_read_mV=0 vcc_set_mV=2500 vcc_reset_mV=0 vcc_wl_read_mV=0 vcc_wl_set_mV=2500 vcc_wl_reset_mV=0` |

| Timing / decode | Value |
|---|---:|
| `ready` fall | 0.37884912 s |
| `ready` rise | 0.39032368 s |
| `TM` rise | 0.39038896 s |
| `ScanInDR` fall | 0.39038944 s |
| `ScanInDL` rise | 0.39039744 s |
| `ScanInDL` fall | 0.39039792 s |
| `ScanInDR` rise | 0.39039840 s |
| `TM` to `ScanInDR` fall | 0.48 us, 1.00 clk |
| `ScanInDL` high width | 0.48 us, 1.00 clk |
| `ScanInDR` low width | 8.96 us, 18.67 clk |
| Active rising edges while `ScanInDR` low | 18 |
| Decoded word | `0x8000` |
| LSB-first data bits | `0000000000000001` |
| 16th data bit | 1 |
| Extra active sample | 0 |

| Current source | Mean | Min | Max | Span | Samples |
|---|---:|---:|---:|---:|---:|
| Saleae set shunt, full run | 317.15 uA | -14.00 uA | 770.00 uA | 784.00 uA | 1265625 |
| Saleae reset shunt, full run | 306.13 uA | 206.00 uA | 755.00 uA | 549.00 uA | 1265625 |
| Saleae set shunt, zoom | 403.33 uA | 11.00 uA | 770.00 uA | 759.00 uA | 39 |
| Saleae reset shunt, zoom | 652.62 uA | 635.00 uA | 677.00 uA | 42.00 uA | 39 |
| ADC read, full run | 952.08 uA |  |  |  | 19 |
| ADC set, full run | -25.15 uA |  |  |  | 19 |
| ADC reset, full run | -705.88 uA |  |  |  | 19 |

## 3. Fourth Last Run: `0x0000`, `Vcc_set = 2.5 V`

![Fourth last run timing and currents, PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_125104_fast_saleae_vccset2v5_rerun_currents_same_timescale.png)

![Fourth last run timing and currents, SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_125104_fast_saleae_vccset2v5_rerun_currents_same_timescale.svg)

Artifacts: [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_125104_fast_saleae_vccset2v5_rerun_currents_same_timescale.png), [SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_125104_fast_saleae_vccset2v5_rerun_currents_same_timescale.svg)

| Item | Value |
|---|---|
| Capture directory | `scan_debug_req0000_2026-08-11/capture_125104_fpga_manual_reset_fast_saleae_vccset2v5_rerun` |
| Bitstream SHA | `09E397FECCB5E723D3CD43C06FB74155DE95E28CDA9F1BA4BE1267C2CA50EE69` |
| Rail command result | `vcc_read_mV=0 vcc_set_mV=2500 vcc_reset_mV=0 vcc_wl_read_mV=0 vcc_wl_set_mV=2500 vcc_wl_reset_mV=0` |

| Timing / decode | Value |
|---|---:|
| `ready` fall | 0.37884912 s |
| `ready` rise | 0.39032368 s |
| `TM` rise | 0.39038880 s |
| `ScanInDR` fall | 0.39038928 s |
| `ScanInDR` rise | 0.39039840 s |
| `ScanInDL` edges near packet | 0 |
| `TM` to `ScanInDR` fall | 0.48 us, 1.00 clk |
| `ScanInDR` low width | 9.12 us, 19.00 clk |
| Active rising edges while `ScanInDR` low | 18 |
| Decoded word | `0x0000` |
| LSB-first data bits | `0000000000000000` |
| 16th data bit | 0 |
| Extra active sample | 0 |

| Current source | Mean | Min | Max | Span | Samples |
|---|---:|---:|---:|---:|---:|
| Saleae set shunt, full run | 229.82 uA | -20.00 uA | 518.00 uA | 538.00 uA | 1265625 |
| Saleae reset shunt, full run | 345.94 uA | 222.00 uA | 775.00 uA | 553.00 uA | 1265625 |
| Saleae set shunt, zoom | 330.12 uA | -14.00 uA | 455.00 uA | 469.00 uA | 40 |
| Saleae reset shunt, zoom | 753.58 uA | 744.00 uA | 765.00 uA | 21.00 uA | 40 |
| ADC read, full run | 1013.01 uA |  |  |  | 13 |
| ADC set, full run | -25.23 uA |  |  |  | 13 |
| ADC reset, full run | -801.30 uA |  |  |  | 13 |

## 4. Third Last Run: `0x0000`, `Vcc_set = 1.7 V`

![Third last run timing and currents, PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_161357_fast_saleae_vccset1v7_rerun_currents_same_timescale.png)

![Third last run timing and currents, SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_161357_fast_saleae_vccset1v7_rerun_currents_same_timescale.svg)

Artifacts: [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_161357_fast_saleae_vccset1v7_rerun_currents_same_timescale.png), [SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_161357_fast_saleae_vccset1v7_rerun_currents_same_timescale.svg)

| Item | Value |
|---|---|
| Capture directory | `scan_debug_req0000_2026-08-11/capture_161357_fpga_manual_reset_fast_saleae_vccset1v7_rerun` |
| Bitstream SHA | `B1BEC264F38ED990B7F0D0162B3111E6DEDE2A0B2024E8F2BD326568231F66A4` |
| Rail command result | `vcc_read_mV=0 vcc_set_mV=1700 vcc_reset_mV=0 vcc_wl_read_mV=0 vcc_wl_set_mV=2500 vcc_wl_reset_mV=0` |

| Timing / decode | Value |
|---|---:|
| `ready` fall | 0.37884880 s |
| `ready` rise | 0.39032320 s |
| `TM` rise | 0.39038848 s |
| `ScanInDR` fall | 0.39038896 s |
| `ScanInDR` rise | 0.39039792 s |
| `ScanInDL` edges near packet | 0 |
| `TM` to `ScanInDR` fall | 0.48 us, 1.00 clk |
| `ScanInDR` low width | 8.96 us, 18.67 clk |
| Active rising edges while `ScanInDR` low | 18 |
| Decoded word | `0x0000` |
| LSB-first data bits | `0000000000000000` |
| 16th data bit | 0 |
| Extra active sample | 0 |

| Current source | Mean | Min | Max | Span | Samples |
|---|---:|---:|---:|---:|---:|
| Saleae set shunt, full run | -143.97 uA | -326.00 uA | -41.00 uA | 285.00 uA | 1265625 |
| Saleae reset shunt, full run | 1.22 uA | -19.00 uA | 32.00 uA | 51.00 uA | 1265625 |
| Saleae set shunt, zoom | -235.20 uA | -289.00 uA | -83.00 uA | 206.00 uA | 40 |
| Saleae reset shunt, zoom | 1.98 uA | -9.00 uA | 12.00 uA | 21.00 uA | 40 |
| ADC read, full run | -506.38 uA |  |  |  | 84 |
| ADC set, full run | -26.20 uA |  |  |  | 84 |
| ADC reset, full run | -34.42 uA |  |  |  | 84 |

## 5. Second Last Run: `0x8000`, `Vcc_set = 2.5 V`

![Second last run timing and currents, PNG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_163107_fast_saleae_vccset2v5_rerun_currents_same_timescale.png)

![Second last run timing and currents, SVG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_163107_fast_saleae_vccset2v5_rerun_currents_same_timescale.svg)

Artifacts: [PNG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_163107_fast_saleae_vccset2v5_rerun_currents_same_timescale.png), [SVG](scan_debug_req8000_2026-08-11/fpga_scan8000_manual_reset_163107_fast_saleae_vccset2v5_rerun_currents_same_timescale.svg)

| Item | Value |
|---|---|
| Capture directory | `scan_debug_req8000_2026-08-11/capture_163107_fpga_manual_reset_fast_saleae_vccset2v5_rerun` |
| Bitstream SHA | `08CD5196EAF9EEC5B04FEABFC96B28F3509BE23D61278EADC782711ED7C07D4D` |
| Rail command result | `vcc_read_mV=0 vcc_set_mV=2500 vcc_reset_mV=0 vcc_wl_read_mV=0 vcc_wl_set_mV=2500 vcc_wl_reset_mV=0` |

| Timing / decode | Value |
|---|---:|
| `ready` fall | 0.37884880 s |
| `ready` rise | 0.39032320 s |
| `TM` rise | 0.39038848 s |
| `ScanInDR` fall | 0.39038896 s |
| `ScanInDL` rise | 0.39039696 s |
| `ScanInDL` fall | 0.39039744 s |
| `ScanInDR` rise | 0.39039792 s |
| `TM` to `ScanInDR` fall | 0.48 us, 1.00 clk |
| `ScanInDL` high width | 0.48 us, 1.00 clk |
| `ScanInDR` low width | 8.96 us, 18.67 clk |
| Active rising edges while `ScanInDR` low | 18 |
| Decoded word | `0x8000` |
| LSB-first data bits | `0000000000000001` |
| 16th data bit | 1 |
| Extra active sample | 0 |

| Current source | Mean | Min | Max | Span | Samples |
|---|---:|---:|---:|---:|---:|
| Saleae set shunt, full run | -126.54 uA | -306.00 uA | -26.00 uA | 280.00 uA | 1265625 |
| Saleae reset shunt, full run | 0.77 uA | -19.00 uA | 32.00 uA | 51.00 uA | 1265625 |
| Saleae set shunt, zoom | -95.47 uA | -109.00 uA | -67.00 uA | 42.00 uA | 40 |
| Saleae reset shunt, zoom | 4.03 uA | -9.00 uA | 12.00 uA | 21.00 uA | 40 |
| ADC read, full run | -454.14 uA |  |  |  | 40 |
| ADC set, full run | -25.99 uA |  |  |  | 40 |
| ADC reset, full run | -35.02 uA |  |  |  | 40 |

## 6. Last Run: `0x0000`, `Vcc_set = 1.7 V`

![Last run timing and currents, PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_163942_fast_saleae_vccset1v7_rerun_currents_same_timescale.png)

![Last run timing and currents, SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_163942_fast_saleae_vccset1v7_rerun_currents_same_timescale.svg)

Artifacts: [PNG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_163942_fast_saleae_vccset1v7_rerun_currents_same_timescale.png), [SVG](scan_debug_req0000_2026-08-11/fpga_scan0000_manual_reset_163942_fast_saleae_vccset1v7_rerun_currents_same_timescale.svg)

| Item | Value |
|---|---|
| Capture directory | `scan_debug_req0000_2026-08-11/capture_163942_fpga_manual_reset_fast_saleae_vccset1v7_rerun` |
| Bitstream SHA | `2C47005DA1BB25BB696EA1CE95FACE6D43EDD2EA6CE1FEE8C23EC1C0222051B5` |
| Rail command result | `vcc_read_mV=0 vcc_set_mV=1700 vcc_reset_mV=0 vcc_wl_read_mV=0 vcc_wl_set_mV=2500 vcc_wl_reset_mV=0` |

| Timing / decode | Value |
|---|---:|
| `ready` fall | 0.37884896 s |
| `ready` rise | 0.39032336 s |
| `TM` rise | 0.39038864 s |
| `ScanInDR` fall | 0.39038912 s |
| `ScanInDR` rise | 0.39039824 s |
| `ScanInDL` edges near packet | 0 |
| `TM` to `ScanInDR` fall | 0.48 us, 1.00 clk |
| `ScanInDR` low width | 9.12 us, 19.00 clk |
| Active rising edges while `ScanInDR` low | 18 |
| Decoded word | `0x0000` |
| LSB-first data bits | `0000000000000000` |
| 16th data bit | 0 |
| Extra active sample | 0 |

| Current source | Mean | Min | Max | Span | Samples |
|---|---:|---:|---:|---:|---:|
| Saleae set shunt, full run | -57.13 uA | -156.00 uA | -10.00 uA | 146.00 uA | 1265625 |
| Saleae reset shunt, full run | 71.13 uA | 43.00 uA | 167.00 uA | 124.00 uA | 1265625 |
| Saleae set shunt, zoom | -87.08 uA | -140.00 uA | -21.00 uA | 119.00 uA | 40 |
| Saleae reset shunt, zoom | 135.30 uA | 120.00 uA | 146.00 uA | 26.00 uA | 40 |
| ADC read, full run | -293.96 uA |  |  |  | 21 |
| ADC set, full run | -28.52 uA |  |  |  | 21 |
| ADC reset, full run | -211.36 uA |  |  |  | 21 |

## Observations

| Comparison | Observation |
|---|---|
| Packet decode | Both `0x0000` and `0x8000` decode correctly in these captures. For `0x8000`, `ScanInDL` is high for one clock period at the 16th data bit. |
| Set-current sensitivity | The 2.5 V `Vcc_set` runs generally show larger positive Saleae set-shunt zoom current when the set shunt is connected. |
| Reset-shunt behavior | Reset-shunt current changes significantly between runs even though `Vcc_reset=0 V`; this should be treated as measurement context/coupling unless confirmed with a dedicated reset-rail isolation run. |
| ADC vs Saleae timing | ADC full-run means are useful for rail context, but Saleae is the timing-authoritative measurement for scan-debug microsecond behavior. |
