# Bi-Slice
Bi-Slice - Intelligent Fiber-Reinforced Composite 3D Printing Slicer; Bi-Modal Stress Based Fiber Oriantation

<img width="1049" height="441" alt="image" src="https://github.com/user-attachments/assets/ca9b72a7-7bd0-446b-8bf8-e3e26a38b1ee" />

Bi-Slice is a Windows desktop application that converts 3D STL models into G‑code using a 6‑step workflow:

1. Upload STL  
2. Create Mesh  
3. Assign Boundary Conditions (BC)  
4. Run FEA  
5. G-code Processing  
6. Save G-code / Export Report

---

## 1. System Requirements

- **Operating system**: Windows 10 or Windows 11 (64‑bit)
- **RAM**: 8 GB minimum (16 GB recommended for large models)
- **Disk space**: At least 2 GB free
- **GPU (optional)**: NVIDIA GPU with CUDA for GPU‑accelerated steps (if enabled in the app)

---

## Basic Workflow inside Bi-Slice

Once the app is running:

- **Tab 1 – Upload STL**
  - Click **“Select STL File”**.
  - Choose your STL file.
  - The app computes and displays a 2D projection of the part.

- **Tab 2 – Create Mesh**
  - Optionally adjust **Grid Spacing (mm)**.
  - Click **“Generate Mesh”**.
  - The mesh is created, visualized, and saved as `fea_mesh.msh`.

- **Tab 3 – Assign BC**
  - Click **“Open BC Assignment”**.
  - Assign displacements/loads at mesh nodes.
  - For loading apply **Load**, **NOT DISPLACEMENT!!!!!!!!**.
  - Do not forget to **Save your BCs** (stored in `boundary_conditions.json`), and the BC visualization updates in the main window.

- **Tab 4 – Run FEA**
  - Adjust **material properties** (E, ν, E1, E2, ν12, iteration count) if needed.
  - Optionally enable **“Use GPU”** if you have a compatible GPU.
  - Click **“Run FEA”**.
  - When complete, review the **principal stress plots** in the FEA results tabs.

- **Tab 5 – G-code Processing**
  - Set **Line Thickness**, **Quality Factor**, and **Threshold**.
    - Click **“Process G-code”**.
  - Watch the multi‑stage progress bars and then review the resulting plots in the G‑code tabs.

- **Tab 6 – Save G-code / Export Report**
  - Click **“Visualize G-code”** to generate and display the combined toolpath.
  - Click **“SAVE G-CODE”** to export `combined_infill.gcode` to a location of your choice.
  - Click **“EXPORT REPORT”** to save a high‑resolution **PDF** or **Word** report summarizing the steps and results.

---

## 2. Files Created by the App

During a typical run, Bi-Slice will create/update:

- `fea_mesh.msh` – Finite element mesh file.
- `boundary_conditions.json` – Saved boundary conditions.
- `combined_infill.gcode` – Generated G-code for printing.
- `bi_slice.log` – Log file with technical details (useful for debugging).


