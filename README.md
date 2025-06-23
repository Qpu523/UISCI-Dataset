# UISCI Dataset: Urban Intersection Safety-Critical Interaction Dataset

This repository hosts the **UISCI Dataset**, a large-scale, high-resolution dataset of **vehicle-pedestrian near-miss interactions at urban intersections**, generated using our proposed **Two-Stage Multi-Agent SST-DDPG framework** in CARLA.

---

## 🧠 Framework Overview

![Framework Overview](https://github.com/Qpu523/HiRISC-Dataset/blob/7ac52fe8a27fbb071942795e77c5461db8f661d2/Config/Picture11.png)

The Two-Stage MA-SST-DDPG framework consists of:

- **Stage 1: Risk Scenario Generation using CurvTTC Trigger**  
  In diverse CARLA intersection scenarios, we simulate thousands of AV–pedestrian interactions. When the computed **Curvilinear Time-to-Collision (CurvTTC)** falls below a risk threshold, the interaction is recorded as a **near-miss trajectory**. This produces a high-quality dataset in evasive maneuvers and collision-avoidance behaviors.

- **Stage 2: MA-SST-DDPG Training with Online Learning**  
  The recorded near-miss data is used to **pre-train a multi-agent safe reinforcement learning model**. The trained policy is then deployed in the CARLA environment to **interact with new agents**, and the model is **continuously refined through online learning**, ensuring it adapts to evolving behaviors and generates diverse, realistic, and risky interaction data.
- **Output:** A realistic and scalable dataset of over **80,000 near-miss interaction episodes**, capturing **genuine collision-avoidance behaviors** between vehicles and pedestrians in simulated urban intersections.

---

## 🗺 Simulation Environment

![Simulation Intersections](https://github.com/Qpu523/HiRISC-Dataset/blob/7ac52fe8a27fbb071942795e77c5461db8f661d2/Config/Picture22.png)

We simulate two intersection layouts (**A** and **B**) in CARLA's Town10. Each location contains four vehicle-pedestrian interaction scenarios involving right-turning vehicles and crossing pedestrians.

- 🟩 **Green arrow**: Pedestrian crossing direction  
- 🟥 **Red arrow**: Vehicle right-turn direction

| Scenario ID | Location | Vehicle Turn Direction | Pedestrian Direction |
|-------------|----------|------------------------|----------------------|
| ①           | A        | Right-turn             | East → West          |
| ②           |          |                        | South → North        |
| ③           |          |                        | West → East          |
| ④           |          |                        | North → South        |
| ⑤           | B        | Right-turn             | East → West          |
| ⑥           |          |                        | South → North        |
| ⑦           |          |                        | West → East          |
| ⑧           |          |                        | North → South        |




---

## 📊 Representative Trajectories

![Trajectory Examples](https://github.com/Qpu523/HiRISC-Dataset/blob/7ac52fe8a27fbb071942795e77c5461db8f661d2/Config/Picture33.png)

Red = Pedestrian, Blue = Vehicle. Color gradient = time. The plots highlight different temporal-spatial conflict patterns across 8 scenarios.

---

## 📁 Dataset Structure

- 8 scenario files (e.g., `LocationA_PedCross_S-N.csv`, etc.)
- Each file contains >10,000 episodes
- Recorded at 20 Hz over ~2.6 km pedestrian + ~1.7 km vehicle trajectories

| Field Name         | Description                                 |
|--------------------|---------------------------------------------|
| `count`            | Interaction episode index                   |
| `frame`            | Frame number within the episode             |
| `veh_id`, `ped_id` | Unique identifiers for vehicle and pedestrian |
| `position_x_av`    | Vehicle x-position (m)                      |
| `velocity_y_ped`   | Pedestrian y-velocity (m/s)                 |
| `CurvTTC`          | Curvilinear time-to-collision (s)           |
| ...                | More details in the paper                   |

---

## 📥 Download  Urban Intersection Safety-Critical Interaction Dataset

<table>
<tr>
<th><a href="https://1drv.ms/f/c/your-link-1">Subset 1<br></a>(Pedestrian crossing from South to North)</th>
<th><a href="https://1drv.ms/f/c/your-link-2">Subset 2<br></a>(Pedestrian crossing from North to South)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/1.png" alt="Subset 1" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/2.png" alt="Subset 2" /></td>
</tr>

<tr>
<th><a href="https://1drv.ms/f/c/your-link-3">Subset 3<br></a>(Pedestrian crossing from East to West)</th>
<th><a href="https://1drv.ms/f/c/your-link-4">Subset 4<br></a>(Pedestrian crossing from West to East)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/3.png" alt="Subset 3" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/4.png" alt="Subset 4" /></td>
</tr>

<tr>
<th><a href="https://1drv.ms/f/c/your-link-5">Subset 5<br></a>(Pedestrian crossing from South to North)</th>
<th><a href="https://1drv.ms/f/c/your-link-6">Subset 6<br></a>(Pedestrian crossing from North to South)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/5.png" alt="Subset 5" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/6.png" alt="Subset 6" /></td>
</tr>

<tr>
<th><a href="https://1drv.ms/f/c/your-link-7">Subset 7<br></a>(Pedestrian crossing from East to West)</th>
<th><a href="https://1drv.ms/f/c/your-link-8">Subset 8<br></a>(Pedestrian crossing from West to East)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/7.png" alt="Subset 7" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/8.png" alt="Subset 8" /></td>
</tr>

</table>
---


## 🎯 Turing Test: Human Evaluation of Realism

We conducted a **Turing Test** to assess whether human participants could distinguish between:

- Videos generated by our **Two-Stage MA-SST-DDPG** framework
- Real-world near-miss interaction videos
- CARLA baseline simulation videos 

A total of **51 participants** rated 12 randomized videos (4 per category), and their perception scores were statistically analyzed using **t-tests** and **Kolmogorov–Smirnov (KS) tests**.

📺 **Watch the Evaluation Video**: [YouTube Link](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)

---

### 📊 Table 8: Statistical Comparison of Perceptual Scores Between Video Types

| Group 1               | Group 2               | t-statistic | p-value  | KS statistic | p-value  | Significant Difference |
|:---------------------:|:---------------------:|:-----------:|:--------:|:------------:|:--------:|:----------------------:|
| Carla                 | Two-Stage MA-SST-DDPG | -13.5004    | <0.0001  | 0.4951       | <0.0001  | Yes                    |
| Carla                 | Real world            | -13.6295    | <0.0001  | 0.5294       | <0.0001  | Yes                    |
| Two-Stage MA-SST-DDPG | Real world            | -0.0902     | 0.9282   | 0.0588       | 0.8732   | No                     |


---

### ✅ Interpretation

- Participants **easily distinguished** between **Carla baseline** and both **real** and **Two-Stage MA-SST-DDPG** videos (significant differences).
- However, there was **no statistically significant difference** between the **Two-Stage MA-SST-DDPG** videos and the **real-world** videos (p = 0.9282).
- This confirms that our model-generated interactions were perceived as **visually indistinguishable from real-world behaviors**, validating the realism and effectiveness of our learned near-miss simulation framework.


---

## 📬 Contact

For questions or extended data access:

- **Email:** kxie@odu.edu
- **Email:** qpu001@odu.edu
---



## 📚 Citation

If you use the UISCI Dataset or associated model, please cite the following:

```bibtex


}
```

---


