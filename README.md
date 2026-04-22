# VC-Skills
Collection of Claude Cowork skills for venture capital workflows. 

## How to Use
[2–3 lines: clone repo, drop skill folder into Cowork, point Claude at it]

## Principles
1. **Automation vs Co-Worker mode** — every skill declares its execution mode. 
   Automation runs end-to-end without interruption. Co-Worker pauses at defined 
   gates for human judgment before proceeding.
2. **Reference files as live inputs** — skills accept external reference files 
   (e.g. a firm context file, investment criteria, target lists) rather than 
   hardcoding assumptions. Swap the reference file, change the output behaviour.
3. **Pipeline logic** — skills can be designed as a chain. Output from one skill is 
   valid input for the next. Go from Screening -> Evaluation -> Due Diligence.
