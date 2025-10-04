# UISCI Dataset: Urban Intersection Safety-Critical Interaction Dataset

This repository hosts the **UISCI Dataset**, a large-scale, high-resolution dataset of **vehicle-pedestrian near-miss interactions at urban intersections**, generated using our proposed **Three-stage Multi-Agent SST-DDPG framework** in CARLA.

---

## 🧠 Framework Overview

![Framework Overview](https://github.com/Qpu523/UISCI-Dataset/blob/e9974f2cec9b20d5c204afeada061f4466bd595b/Config/Framework.png)

The three-stage framework integrates real-world data with simulation to generate realistic and diverse safety-critical scenarios.

-   **Stage 1: Pre-training with Real-World Data**
    The process begins by pre-training multi-agent state-space Transformer-enhanced DDPG (MA-SST-DDPG) agents on real-world safety-critical data. This allows the agents to learn human-like, interactive evasive behaviors from actual near-miss events.

-   **Stage 2: Online Learning in a Simulation Environment**
    The pre-trained agents are deployed in the CARLA simulator, where they encounter a wide range of high-risk scenarios. The agents continue to learn and adapt through online reinforcement learning, which refines their policies and narrows the gap between simulation and reality.

-   **Stage 3: CARLA-Based Large-Scale Data Generation**
    Using the refined and adapted model from Stage 2, we generate a large-scale dataset in CARLA across multiple intersection scenarios. This stage produces a diverse, high-resolution dataset of safety-critical interactions.
-   **Output:** A realistic and scalable dataset of over **163,000 high-resolution interaction episodes**, capturing authentic collision avoidance behaviors between vehicles and pedestrians in simulated urban intersections.

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
- Data continues to update
<table>
<tr>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EZLKA9aphE1MtSvYtt_X0BQBnmWgYIpkq2zkTFlhZeXAeQ?e=208yPU">Subset 1<br></a>(Pedestrian crossing from South to North)</th>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EZ5Z762JYNxKvoxKIaVXB1QBVuBM88AZAsFnzWO7Ftw1Uw?e=Iym2om">Subset 2<br></a>(Pedestrian crossing from North to South)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/1.png" alt="Subset 1" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/2.png" alt="Subset 2" /></td>
</tr>

<tr>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EfErh2onlUlJvZxgxkYCCXABWJgepIjitTtlUkO-THiUiA?e=pnWgYS">Subset 3<br></a>(Pedestrian crossing from East to West)</th>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EZffOvhaXmJOhNb_cQMJzxABUcyAcmL9dR8r3pqzKDrEoA?e=JTpWRF">Subset 4<br></a>(Pedestrian crossing from West to East)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/3.png" alt="Subset 3" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/4.png" alt="Subset 4" /></td>
</tr>

<tr>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EdEdQ9Gmi8hEnmOBGYwYLBYBUZxpmOIRgf1zszP_2_mLIw?e=Frr5ft">Subset 5<br></a>(Pedestrian crossing from South to North)</th>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/ETt4aq2QG6tCvC1M09ownC8BZhzcG9amni_h4Kvg87B87Q?e=vFpeh0">Subset 6<br></a>(Pedestrian crossing from North to South)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/5.png" alt="Subset 5" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/6.png" alt="Subset 6" /></td>
</tr>

<tr>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EfErh2onlUlJvZxgxkYCCXABWJgepIjitTtlUkO-THiUiA?e=0WERqL">Subset 7<br></a>(Pedestrian crossing from East to West)</th>
<th><a href="https://1drv.ms/x/c/54547f6bb45158b3/EZzXUzp5DY5Pt9svh2r7wckBBQWsYWCA160THARXESeVUw?e=BXaGNS">Subset 8<br></a>(Pedestrian crossing from West to East)</th>
</tr>
<tr>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/7.png" alt="Subset 7" /></td>
<td align="center"><img src="https://github.com/Qpu523/HiRISC-Dataset/blob/e5532840771f062f3f88ca2029b0ff375d10c609/Config/8.png" alt="Subset 8" /></td>
</tr>

</table>

## 🎬 Generated Videos

We provide a folder containing **144 video examples** of the safety-critical interactions generated by our three-stage framework for reference. Click the link below to access the complete collection.

**[➡️ Download the Video Collection (144 Videos)](https://1drv.ms/f/c/54547f6bb45158b3/EhSml9tsupRNq7yM49ZmEpcBO002VR5-8Jh7GO6dBJgwxA?e=eEFhSw)**



## 🎯 Turing Test: Human Evaluation of Realism

A **Turing Test-inspired study** was conducted to assess whether human participants could distinguish the realism of interactions from three different sources:
-   Videos generated by our **three-stage framework (Refined MA-SST-DDPG)**
-   Videos of **real-world** interactions projected into CARLA
-   Videos from the **default CARLA autopilot**

A total of **51 participants** rated 12 randomized videos (4 per category), and their perception scores were statistically analyzed using **t-tests** and **Kolmogorov–Smirnov (KS) tests**.

📺 **Watch the Demonstration Video**: [YouTube Link](https://www.youtube.com/watch?v=ul8AvVOk0SE)

---

### 📊 Table 8: Statistical Comparison of Perceptual Scores Between Video Types

| Group 1               | Group 2               | t-statistic | p-value  | KS statistic | p-value  | Significant Difference |
|:---------------------:|:---------------------:|:-----------:|:--------:|:------------:|:--------:|:----------------------:|
| CARLA                 | Two-Stage MA-SST-DDPG | -13.5004    | <0.0001  | 0.4951       | <0.0001  | Yes                    |
| CARLA                 | Real world            | -13.6295    | <0.0001  | 0.5294       | <0.0001  | Yes                    |
| Two-Stage MA-SST-DDPG | Real world            | -0.0902     | 0.9282   | 0.0588       | 0.8732   | No                     |


---

### ✅ Interpretation

Participants could **easily distinguish** the unrealistic behaviors of the **CARLA baseline** from both real-world videos and our framework's generated videos (statistically significant differences, p < 0.001).
-   There was **no statistically significant difference** in perceived realism between the **Refined MA-SST-DDPG** videos and the **real-world** videos (p = 0.9282).
-   This confirms that our model-generated interactions were perceived as **indistinguishable from real-world behaviors**, validating the high-fidelity realism of our data generation framework.

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


