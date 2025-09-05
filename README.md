# MIPS-16-Physical-Design
This abstract presents the physical design implementation of a MIPS-16 processor, focusing on achieving optimal performance in terms of operating frequency and silicon area.

The methodology commenced with the definition of Synopsys Design Constraints (SDC), including an initial clock period of 4ns (250 MHz), with input/output delays set at 30% of the clock period and a clock uncertainty of 0.35ns. Iterative synthesis trials were conducted to optimize timing. The initial trial at 4ns yielded a slack of 2.08. Subsequent trials progressively reduced the clock period to 2ns (slack 0.85) and finally to 1ns, achieving a worst-case slack of -0.01, indicating maximum optimization at the synthesis stage. This optimized clock period of 1ns (1GHz) was carried forward into the Place and Route (PnR) flow.

The PnR phase incorporated stringent hard constraints, including the placement of pins on metal4 and metal5 layers, with inputs designated for the top and left sides, and outputs for the right and bottom sides. A T-shaped floorplan was adopted, maintaining an IR drop within 2% and a core utilization of 0.8. Detailed power planning involved the definition of power rings and a power mesh. The PnR flow encompassed floorplanning, powerplanning, placement (including the strategic creation of routing blockages in metal2 to mitigate Design Rule Check (DRC) violations), Clock Tree Synthesis (CTS), and final routing and chip finishing.

Formal verification was performed both post-synthesis and post-PnR to ensure functional equivalence. Timing closure was rigorously pursued using Primetime with accurate RC extraction from StarRC. Hold violations were systematically addressed through Engineering Change Order (ECO) commands, employing cell sizing and buffer insertion techniques. The iterative process of fixing DRCs and timing violations ultimately resulted in a clean timing report.

Key results demonstrate the successful physical implementation of the MIPS-16 design, achieving an operational frequency of 1GHz with a core utilization of 0.8. The total silicon area for the design is 0.03713 mm² (37131.471 µm²). This project highlights a robust physical design methodology capable of delivering high-performance and area-optimized digital circuits.


