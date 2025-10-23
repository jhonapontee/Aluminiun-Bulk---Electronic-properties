# Midterm Project – DFT Study of fcc Aluminum (Al)

This repository contains all scripts, results, and analysis for the **DFT midterm project** carried out at Yachay Tech University.  
The system studied is **fcc Aluminum (Al)** using **VASP** with the **GGA-PBE functional**.  

The workflow follows the project instructions: convergence tests, equation of state (EOS), ground state properties, electronic structure, and comparison with experimental data.

---

## 📂 Repository Contents

- **scripts/** → Bash scripts for automation (`en_cut.sh`, `k_points.sh`, `cell.sh`, `bulk.sh`, etc.)  
- **results/** → Raw and processed VASP outputs (OUTCAR, vasprun.xml, DOSCAR, etc.)  
- **analysis/** → Extracted data, tables, and plots (convergence, EOS, PDOS, band structure).  
- **report/** → Summaries, figures, and comparison with experimental values.  

---

## ⚙️ Methodology

1. **Energy cutoff convergence (ENCUT):**  
   - Tested from 250 eV to 900 eV with a 17×17×17 k-point mesh.  
   - Convergence criterion: ΔE < 1 meV/atom.  

2. **KPOINTS convergence:**  
   - Meshes from 15×15×15 up to 28×28×28.  
   - Convergence criterion: ΔE < 1 meV/atom.  

3. **Equation of State (EOS):**  
   - Volumes generated around the initial value (16.5 Å³ for Al).  
   - Fitted to obtain **Vopt, a₀, B₀, B′**.  

4. **Ground state properties:**  
   - Optimized structure at Vopt.  
   - Symmetry analysis with **FINDSYM**.  
   - Interatomic distances tabulated.  

5. **Electronic structure:**  
   - **PDOS**: decomposition into s, p, d states.  
   - **Charge density**: visualized with VESTA (3×3×3 supercell).  
   - **Band structure**: along high-symmetry path (X–U–W–K–F–L).  

6. **Cohesive energy:**  
   - Computed from bulk and isolated atom energies (15 Å box, 1×1×1 k-point mesh).  

7. **Comparison with experiment:**  
   - Computed values (Vopt, a₀, B₀) compared with Kittel’s *Solid State Physics*.  
   - Percentage error calculated as:  



\[
     \text{error} = \frac{X_c - X_{expt}}{X_{expt}} \times 100
\]



---

## 📊 Results Overview

- **Convergence tests:** Stable ENCUT and KPOINTS identified.  
- **EOS:** Extracted equilibrium volume and bulk modulus.  
- **Ground state:** Correct fcc symmetry confirmed.  
- **Electronic structure:** Al is metallic, with conduction bands crossing the Fermi level.  
- **Cohesive energy:** Consistent with literature values.  
- **Comparison:** Errors with respect to experiment within acceptable range (<5%).  

---

## 🖥️ Usage

To reproduce calculations:

```bash
# ENCUT convergence
bash scripts/en_cut.sh

# KPOINTS convergence
bash scripts/k_points.sh

# EOS calculation
bash scripts/cell.sh

# Ground state
bash scripts/bulk.sh
