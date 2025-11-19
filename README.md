# \[DAC26\] Bus Skew Balancing Benchmark
## Benchmark Description
To emulate new bus routing challenges (e.g., 2D placed bus pins), we developed a new bus routing benchmark by extending the ICCAD 2018 benchmark suite[1]. First, we construct nine distinct netlists varying in bus width and count configurations. Then, for each netlist, we create two floorplan variants, 1D-placed and 2D-placed, by changing die width, height, pin placement, and routing blockages. The 1D set is included specifically to highlight that 2D pin placement exhibits larger intra-bus HPWL variation compared to the 1D case. In total, we provide a set of 18 routing benchmarks designed to evaluate bus routing under different I/O pin configurations:

### 1D_placed_designs (Total 9 benchmarks)
  - bus_XX_1D
      - bus_XX_1D.png
      - bus_XX_1D.tar.gz
      - bus_XX.v
  - 9 benchmarks with conventional 1D pins

### 2D_placed_designs (Total 9 benchmarks)
  - bus_XX_2D
      - bus_XX_2D.png
      - bus_XX_2D.tar.gz
      - bus_XX.v
  - 9 benchmarks with mixed 1D & 2D pins
        
All benchmark layouts were implemented using the commercial tool, Innovus v21.16 [2]. The 2D placed benchmarks were constructed through custom DEF generation.

## Bus Configuration
Each benchmark includes buses with four different bus widths:
- 8-bit, 16-bit, 32-bit, and 64-bit

## Pin Placement
- 1D_placed benchmarks: All input/output pins are placed along the die boundary (M5 layer).
- 2D_placed benchmarks:
  - Input pins remain on the die boundary (M5 layer).
  - Output pins are placed inside the die as 2D pins, modeled after TSV-based connections.
  - Each 2D pin uses a 5 × 5 µm² metal pad on the M5 layer, matching top BEOL via dimensions and routing track pitch.

## Routing and Blockage Configuration
- Detailed routing is performed using [2].
- Routing blockages are inserted on M3 and M4, effectively constraining available routing space for buses.

<p align="center">
  <img src="Table.png" alt="My Table" width=700 legnth=700>
</p>

## Reference
[1] A. Liao, H. Chang, O. Chi, and J. Wang. (2018). ”ICCAD 2018 CAD Contest Obstacle-Aware On-Track Bus Routing” [Online]. Available: https://drive.google.com/file/d/16dNYQDnR9aUZ4F6cs33X-MeWjXOM8vfn/view  
[2] "Cadence Innovus User Guide," http://www.cadence.com.
