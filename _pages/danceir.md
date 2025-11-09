---
layout: page
title: DanceIR
permalink: /danceir/
nav: true
---

# DanceIR  
*A Research Framework for Dance Information Retrieval and Motion-Based Tempo Estimation*

DanceIR is a research framework and Python toolbox for analyzing rhythmic structure directly from **dance movement**, without relying on audio. It combines principles from Music Information Retrieval (MIR), signal processing, and movement science to extract **rhythmic anchors**, estimate **dance-derived tempo**, and study **body–music synchrony** using motion capture and pose data.

This page provides an overview of the research, method, and supplementary demonstrations accompanying the DanceIR toolbox and related publications.

---

## Overview

Natural human movement contains strong rhythmic structure. Dancers often articulate **beats**, **subdivisions**, and **metrical layers** through coordinated hand, foot, and torso motions. DanceIR formalizes these patterns as *rhythmic anchors*—kinematic events such as:

- trajectory endpoints (zero-velocity points),
- velocity peaks,
- motion-energy peaks.

These anchors form periodic sequences that reveal the dancer’s **internal pulse**. DanceIR tracks these sequences over time and derives a **global tempo estimate** aligned with the dancer’s movement patterns.

The framework is designed for research on dance–music interaction, multimodal rhythm analysis, and embodied entrainment.

---

## Method Summary

### **1. Rhythmic Anchor Extraction**
DanceIR identifies movement anchors from pose or motion-capture data.  
Common anchor types include:
- **Zero-velocity anchors** (trajectory reversals)
- **Peak-velocity anchors**
- **Motion-energy peaks**
- **Foot contact events** (from foot-ground interaction)

These sequences represent the dancer’s primary periodic motions.

---

### **2. Periodicity & Tempo Estimation**
Tempo is estimated by analyzing anchor sequences using:
- inter-onset interval (IOI) statistics,
- windowed periodicity analysis,
- log-scaled tempo tracking,
- a novel **Octave-Invariant Accuracy metric**.

DanceIR outputs both:
- **continuous tempo curves**, and  
- **global tempo estimates** per performance.

---

### **3. Octave-Invariant Metric (Γ<sub>OI</sub>)**
To quantify dance-derived tempo accuracy, DanceIR introduces the continuous, log-scaled **Octave-Invariant Accuracy**:

- Perfect alignment at half-time, original tempo, or double-time → Γ<sub>OI</sub> = 1  
- Outside the tolerance band → Γ<sub>OI</sub> = 0  
- A tempo estimate is considered a *hit* when Γ<sub>OI</sub> > 0

This provides a musically meaningful evaluation consistent with metrical hierarchy.

---

## Supplementary Videos

Below are selected demonstrations generated using DanceIR.  
Videos illustrate anchor extraction, periodicity tracking, global tempo estimation, and cross-anchor comparisons.

> **Note:** Videos hosted in this repository:  
> `https://sagar0dutta.github.io/danceir-supplementary/videos/`

### **Anchor Extraction Example**
<video controls width="100%">
  <source src="/danceir-supplementary/videos/anchor_extraction.mp4" type="video/mp4">
</video>
*Identification of zero- and peak-velocity anchors from hand trajectories.*

---

### **Global Tempo Estimation (Γ<sub>OI</sub>)**
<video controls width="100%">
  <source src="/danceir-supplementary/videos/tempo_estimation.mp4" type="video/mp4">
</video>
*Tempo tracking using rhythmic anchors and octave-invariant scoring.*

---

### **Comparison Across Anchor Types**
<video controls width="100%">
  <source src="/danceir-supplementary/videos/anchor_comparison.mp4" type="video/mp4">
</video>
*Different body segments emphasize different metrical layers; DanceIR unifies them.*

---

## DanceIR Toolbox

DanceIR is available as a Python package:

```bash
pip install danceir
