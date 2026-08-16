
# **MisNotas**

## Software Requirements Specification

- Version: 0.1
- Status: Draft
- Author: Gabriel Cuartas B.
- Date: August 16th, 2026

## 1. Introduction

### 1.1. Purpose

This Software Requirements Specification (SRS) document defines the functional and non-functional requirements for MisNotas, which is an academic performance management system. 

This document serves as the primary reference for the design, development, testing, and validation of the system.

### 1.2. Scope

MisNotas is an academic performance management system designed to help students organize, monitor, and evaluate their academic performance throughout their semesters. The system allows users to manage multiple semesters and the subjects within them, register grading structures, record grades, define academic goals, and monitor their progress toward those goals.

Version 1.0 (hereafter referred to as v1.0) includes user account management, semester and subject management, assessment and grade tracking, customizable grading structures, academic goal management, grade calculations and projections, risk detection, periodic and on-demand reports, and historical performance analysis. The system automatically recalculates dependent results whenever relevant academic data is modified.

MisNotas supports assessment components with different weighting structures, including groups of multiple individual assignments or activities. It provides current grades, projected final grades, expected and minimum scenarios, grades required on remaining work, semester average projections, and progress toward user-defined goals.

v1.0 is intended to provide a centralized and accessible alternative to manually maintaining academic performance information in spreadsheets or similar tools. The system does not include AI agents or require users to manually perform the calculations and projections provided by the system.

The scope of v1.0 is limited to the academic performance management functionality defined in this document. Features not explicitly included in the v1.0 requirements are considered outside the scope of this version.

### 1.3. Intended Audience

This document is intended for: 

* Software developers
* Stakeholders
* Testers
* Users interested in understanding the system's functionality

### 1.4. Definitions

* **MisNotas:** The academic performance management system.
* **Semester:** An academic period containing subjects.
* **Subject:** An academic course belonging to a semester.
* **Assessment component:** A graded component contributing a percentage of a subject's final grade.
* **Assessment group:** An assessment component containing multiple individual pieces of work that collectively contribute to the component's grade, such as a group of workshops.
* **Current grade:** The grade calculated using the graded assessment components currently recorded for a subject. For a semester, the current average is calculated using the current grades of its subjects weighted according to their credits.
* **Projected final grade:** An estimated final grade calculated from the grades currently recorded and the remaining ungraded assessment components.
* **Minimum passing grade:** The lowest grade that a student can obtain in a subject while still passing it, as defined by the academic institution or course configuration.
* **Goal:** A target academic grade defined by the user for either an individual subject or an entire semester. Goals have a user-defined name and can be modified within the limits defined by the system.
* **At risk:** A subject is at risk when its projected final grade falls within the range: Minimum passing grade $\leq$ projected final grade $\leq$ minimum passing grade + $0.5$. Let $M_p$ be the mimimum grade required to pass and $x$ the projected final grade:
  $$
  M_p \leq x \leq (M_p + 0.5)
  $$
* **v1.0:** The first production release of MisNotas containing all functionality defined within the V1 scope of this SRS.

## 2. Product Overview

## 3. System Scope

## 4. Functional Requirements
