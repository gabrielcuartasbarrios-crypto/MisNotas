
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

MisNotas is an academic performance management system designed to help students organize, monitor, and evaluate their academic performance throughout their academic period. The system allows users to manage multiple academic periods and the subjects within them, register grading structures, record grades, define academic goals, and monitor their progress toward those goals.

Version 1.0 (hereafter referred to as v1.0) includes user account management, academir period and subject management, assessment and grade tracking, customizable grading structures, academic goal management, grade calculations and projections, risk detection, periodic and on-demand reports, and historical performance analysis. The system automatically recalculates dependent results whenever relevant academic data is modified.

MisNotas supports assessment components with different weighting structures, including groups of multiple individual assignments or activities. It provides current grades, projected final grades, expected and minimum scenarios, grades required on remaining work, academic period average projections, and progress toward user-defined goals.

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
* **Academic Period:** A defined period of academic study containing subjects.
* **Subject:** An academic course belonging to an academic period.
* **Assessment component:** A graded component contributing a percentage of a subject's final grade.
* **Assessment group:** An assessment component containing multiple individual pieces of work that collectively contribute to the component's grade, such as a group of workshops.
* **Current grade:** The grade calculated using the graded assessment components currently recorded for a subject. For an acaemic period, the current average is calculated using the current grades of its subjects weighted according to their credits.
* **Projected final grade:** An estimated final grade calculated from the grades currently recorded and the remaining ungraded assessment components.
* **Minimum passing grade:** The lowest grade that a student can obtain in a subject while still passing it, as defined by the academic institution or course configuration.
* **Goal:** A target academic grade defined by the user for either an individual subject or an entire academic period. Goals have a user-defined name and can be modified within the limits defined by the system.
* **At risk:** A subject is at risk when its projected final grade falls within the range: Minimum passing grade $\leq$ projected final grade $\leq$ minimum passing grade + $0.5$. Let $M_p$ be the mimimum grade required to pass and $x$ the projected final grade:

  $$
  M_p \leq x \leq (M_p + 0.5)
  $$
* **v1.0:** The first production release of MisNotas containing all functionality defined within the V1 scope of this SRS.

## 2. Product Overview

### 2.1. Product Description

MisNotas is a web-based academic performance management system that allows users to organize their academic information and keep track of their performance throughout their academic periods. This system centralizes information related to subjects, grades, goals and academic progress while calculating relevant metrics and projections for the user.

### 2.2. Problem Statement

The main problem addressed by MisNotas is the need for students to manually create and maintain systems for tracking their academic performance. These systems are often implemented as spreadsheets containing manually created formulas for calculating grades and averages. These systems generally focus on storing and calculating the values entered by the user, without providing tools for setting academic goals, generating projections, determining the grades required on remaining work, or evaluating progress toward those goals. Also, manually maintained systems can become difficult to manage when the academic structure changes: adding, modifying, or removing subjects and assessment components may require the user to manually update the structure and formulas of the system. MisNotas addresses these limitations by providing an accessible system in which academic information can be managed dynamically while calculations, projections, goals, and progress are handled automatically.

### 2.3. Product Objectives

MisNotas aims to:

1. Consolidate academic information by allowing users to manage their academic periods, subjects, assessments, grades, and goals within a single system.
2. Automate academic calculations by eliminating the need for users to manually create and maintain formulas for grades and averages.
3. Provide academic projections that allow users to understand their expected outcomes and determine the grades required on remaining work.
4. Support academic goal management at both the subject and academic-period levels.
5. Provide actionable information about academic performance through progress indicators, risk detection, and reports.
6. Support flexible grading structures, including assessment components and groups with different weighting configurations.
7. Preserve historical academic information and allow users to compare their performance across academic periods.

### 2.4. Target Users

The primary target users of MisNotas are students who want to organize and monitor their academic performance, since the system is designed to support students in different educational environments, including schools and universities, and is not restricted to a specific academic-period structure. The primary user is responsible for entering and managing their own academic information, while MisNotas performs the corresponding calculations, projections, and analysis automatically.

### 2.5. Product Characteristics

* **Accessibility:** The system should be simple to configure and use while allowing advanced customization when required.
* **Automation:** Academic calculations, projections, and dependent results should be generated automatically.
* **Flexibility:** Users should be able to adapt academic periods, subjects, assessment components, and assessment groups to their specific grading structures.
* **Dynamic behavior:** Changes to academic information should automatically update all dependent calculations and results.
* **Centralization:** Academic information should be maintained within a single system rather than requiring multiple manually maintained tools.
* **Simplicity:** The system should present academic performance, projections, goals, and warnings in a way that is easy for users to understand.

## 3. System Scope

### 3.1. In Scope

* User account management
* Academic period management
* Subject management
* Assessment component management
* Assessment groups
* Grade management
* Subject goals
* Academic-period goals
* Grade calculations
* Grade projections
* Required-grade calculations
* Subject at-risk detection
* Goal progress tracking
* Subject and academic period performance reports
* Historical performance
* Credit-weighted comparisons
* Dynamic recalculation of dependent results when academic data is added, modified, or deleted
* Persistent storage of user academic data

### 3.2. Out of Scope

- AI agents or autonomous AI-based functionality
- Requiring users to manually calculate grades, averages, projections, or other metrics that MisNotas is designed to calculate automatically
- Automatic retrieval/synchronization of grades from university/school platforms
- Integration with external learning management systems (LMS) or university information systems
- Institutional academic administration
- Social features between users
- AI-generated academic advice

## 4. Functional Requirements
