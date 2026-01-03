# Subsurface Resolution Enhancement via MIMO Virtual Array Synthesis

## 1. Project Title
**Subsurface Resolution Enhancement via MIMO Virtual Array Synthesis**

## 2. Objective
To develop a Python-based simulation that calculates the spatial positions of virtual elements in a MIMO (Multiple-Input Multiple-Output) radar system and visualizes the resulting aperture expansion. This allows for higher angular resolution without increasing the number of physical sensors.

## 3. Geophysical Context
In Ground Penetrating Radar (GPR), the ability to resolve two closely spaced objects (such as parallel utility pipes) depends on the size of the array's aperture. By using a MIMO configuration, we create a **Virtual Array** in which each virtual element represents the effective phase center of a distinct Transmit-Receive (TX-RX) pair.

## 4. Technical Roadmap & Learning Goals

### Phase A: Mathematical Modeling
*   **Coordinate Geometry:** Define positions for a set of $M$ transmitters and $N$ receivers (e.g., a "Minimum Redundancy Array" or a simple linear sparse layout).
*   **Synthesis Algorithm:** Implement the vector addition of TX and RX coordinates. The virtual element position for the $i$-th transmitter and $j$-th receiver is calculated as:
    $$POS_{virtual} = \frac{POS_{TX,i} + POS_{RX,j}}{2}$$
*   **Redundancy Analysis:** Identify and address overlapping virtual elements that may arise when physical spacing is not optimized.

### Phase B: Data Science Integration (Pandas & Seaborn)
*   **Data Structuring:** Store TX, RX, and Virtual positions in a Pandas DataFrame. Use categorical labeling to distinguish antenna types.
*   **Seaborn Visualization:**
    *   Use `sns.scatterplot()` to plot the 1D or 2D array layout.
    *   Map the `hue` and `style` parameters to **"Antenna Type"** to visualize the "physical vs. virtual" relationship.
    *   Create a **"Density Plot"** of virtual elements to identify the **"effective aperture"** and gaps in the array.

### Phase C: Evaluation Metrics
*   **Aperture Gain:** Calculate the ratio of the virtual array length to the physical array length.
*   **Resolution Prediction:** Estimate the theoretical angular resolution improvement using the formula:
    $$\theta \approx \frac{\lambda}{D}$$
    where $D$ is the new virtual aperture size.

## 5. Expected Outcomes
*   A reusable Python script capable of testing different **MIMO geometries** (e.g., cross-arrays, box arrays, or random sparse arrays).
*   High-quality **Seaborn plots** demonstrating a deep understanding of geophysical signal processing.
*   A foundational dataset of virtual positions for use in subsequent Subsurface Imaging projects.

## 6. Required Tools (2026 Stack)
*   **Python 3.12+**
*   **Pandas:** For managing complex multi-static pairings.
*   **Seaborn/Matplotlib:** For high-fidelity geophysical visualization.
*   **NumPy:** For vectorized spatial calculations.
