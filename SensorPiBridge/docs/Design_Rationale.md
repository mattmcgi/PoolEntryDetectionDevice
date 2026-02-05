## Design Rationale

### Trace Width
- Supply rail max current: 1.25 mA  
- I²C max current: 0.7 mA  
- Both currents are very small, so I used a standard width of **10 mil**

### Via Size
- Small currents and low inductance make standard vias acceptable  
- Used **12 mil drill, 24 mil pad**, tented

### Routing Power Across SDA/SCL
- **Option 1:** 4-layer board with separate power/ground planes  
  - Overkill for this simple circuit
- **Option 2:** Route trace under a component (GH connector or resistor)  
  - Bad practice and difficult to solder by hand
- **Option 3:** 2-layer board, ground plane on bottom, briefly route power under trace, pour ground plane around it  
  - Chosen solution; practical and obvious in hindsight

### Problems Encountered
- **Pinout issues:**  
  - Used 2×20 female header for Raspberry Pi HAT  
  - Initially, header pins didn’t match Pi pinout due to bottom-side placement  
  - Solution: Adjusted schematic manually to match the Pi, rather than mirroring PCB footprint
