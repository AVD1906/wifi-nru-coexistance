# Simulation-based Performance Analysis of an NR-U and WiFi 
Coexistence System in the Presence of Hidden Nodes 
This repository is a practical extension of the original coexistence study. The paper used a MATLAB-based model, while this project builds a real network environment in ns-3 to study the same problem more realistically.

## What this project studies

The goal is to analyze how NR-U and Wi-Fi share the same wireless channel and affect each other in terms of:

- NR-U throughput and delay
- Wi-Fi throughput and delay
- sensing distance effects
- node density effects
- packet arrival-rate effects

## What is different from the paper

The original work was based on MATLAB. In this repository, we implement the coexistence scenario in ns-3 with:

- a shared wireless channel
- configurable NR-U and Wi-Fi nodes
- realistic PHY/MAC behavior
- packet traffic generation
- throughput and delay measurement

## The eight plot conditions created

The repository generates eight figures by varying key parameters:

- Figures 1 and 2: NR-U data rate sweep
- Figures 3 and 4: NR-U sensing distance sweep
- Figures 5 and 6: node density sweep
- Figures 7 and 8: packet arrival-rate sweep

These results are stored in the figure folders as CSV files and plotted using Python scripts.

## Constant arrival-rate variant

A second version is included for a more controlled traffic model. In this variant, packet arrivals are made  regular by using a constant-arrival setup instead of the more bursty/exponential-style behavior. This helps compare how coexistence behaves under steady traffic versus more variable traffic.

## Repository contents

- NS-3_Simulation_(Network_Environment)/
  - nru-wifi-coex.cc: main ns-3 simulation source
  - Fig_1_and_2/, Fig_3_and_4/, Fig_5_and_6/, Fig_7_and_8/: scripts, CSV results, and plots
  - nru-capture.pcap and wifi-capture.pcap: packet capture files for analysis

- NS-3_Simulation_(Network-Environment)_Constant_Arrival/
  - nru-wifi-coex.cc: modified version with constant-arrival traffic behavior
  - Fig_1_and_2/, Fig_3_and_4/, Fig_5_and_6/: corresponding result and plotting folders
  - nru-capture-sim-changed.pcap and wifi-capture-sim-changed.pcap: capture files for the modified setup

- report.pdf and research paper.pdf
  - reference documents for the original study and the report context

## How to run

Prerequisites:

- ns-3 installed and built
- Python 3
- pandas and matplotlib

Example:

```bash
./ns3 build scratch/nru-wifi-coex.cc
./ns3 run "scratch/nru-wifi-coex.cc --arrivalRate=3.0 --simTime=5"
```




