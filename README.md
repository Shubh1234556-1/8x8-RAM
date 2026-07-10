# RAM8_8 — 8x8 Synchronous RAM (Verilog)

A simple 8-word × 8-bit synchronous RAM module, written in Verilog as an introductory RTL design project.

## Features
- 8x8 internal memory array (`mem[7:0]`, each 8 bits wide)
- Synchronous read/write, controlled by `clk`
- `wr_enb` selects write (1) or read (0)
- Active-high asynchronous reset clears all memory

## Ports

| Signal    | Dir | Width | Description        |
|-----------|-----|-------|---------------------|
| clk       | in  | 1     | Clock                |
| rst       | in  | 1     | Async reset (active high) |
| wr_enb    | in  | 1     | Write enable          |
| wr_addr   | in  | 3     | Write address (0–7)  |
| data_in   | in  | 8     | Data to write         |
| rd_addr   | in  | 3     | Read address (0–7)    |
| data_out  | out | 8     | Data read out         |

## How it works
On every rising edge of `clk`: if `rst` is high, memory is cleared; else if `wr_enb` is high, `data_in` is written to `mem[wr_addr]`; otherwise, `mem[rd_addr]` is read into `data_out`.

## Status
First Verilog project.
