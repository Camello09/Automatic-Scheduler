# AUTOMATIC-SCHEDULER

A Python-based academic scheduling system that generates optimized weekly class schedules using **Google OR-Tools CP-SAT**.

This desktop application helps automate timetable generation for faculty, rooms, sections, and course offerings while enforcing practical academic constraints such as blocked times, lunch breaks, room compatibility, and laboratory scheduling restrictions.

## Overview

Automatic Scheduler is designed for academic departments that need a faster and more reliable way to prepare class schedules. Instead of manually arranging assignments manually, the system reads structured CSV input files and produces a feasible timetable through constraint-based optimization.

The application also provides validation tools, timetable viewing, CSV export, and sample input generation.

## Key Features

- Generates optimized schedules using **Google OR-Tools CP-SAT**
- Assigns faculty, rooms, and class offerings automatically
- Prevents conflicts in:
  - faculty schedules
  - room schedules
  - section schedules
- Enforces faculty blocked times
- Enforces room blocked times
- Protects the lunch break period
- Prevents laboratory subjects from being scheduled on **Fridays**
- Keeps split sessions on different days
- Maintains single-faculty continuity per offering
- Exports generated schedules to CSV
- Displays weekly timetable views by:
  - Section
  - Faculty
  - Room
- Generates sample CSV templates for testing

## Technology Stack

- **Python**
- **Tkinter**
- **Google OR-Tools CP-SAT**
- **CSV-based data input**
- **Threaded schedule generation for UI responsiveness**

## Optimization Engine

This project uses **Google OR-Tools CP-SAT**, a solver for complex scheduling and constraint satisfaction problems.

**CP-SAT** stands for:

- **Constraint Programming**
- **Satisfiability**

It is well suited for academic scheduling because it can evaluate many possible combinations while respecting hard constraints and optimizing schedule quality.

## Constraints Enforced

The scheduler currently enforces the following rules:

- No faculty time conflicts
- No room time conflicts
- No section time conflicts
- Faculty load must not exceed maximum units
- Faculty blocked times must be respected
- Room blocked times must be respected
- Lunch break must remain free
- Split sessions of the same offering must be placed on different days
- Each offering must remain under one faculty member only
- Room type must match the required offering type
- Room capacity must be sufficient for section size
- Laboratory subjects are not allowed on **Fridays**

## Required Input Files

The system uses four CSV files:

- `faculties.csv`
- `rooms.csv`
- `sections.csv`
- `offerings.csv`

### Faculties CSV

**Required columns:**
- `faculty_id`
- `name`
- `max_units`

**Optional columns:**
- `qualified_courses`
- `availability`
- `unavailable`
- `preferred_rooms`

### Rooms CSV

**Required columns:**
- `room_id`
- `room_name`
- `capacity`
- `room_type`

**Optional columns:**
- `priority`
- `unavailable`

### Sections CSV

**Required columns:**
- `section_id`
- `section_name`
- `size`

### Offerings CSV

**Required columns:**
- `offering_id`
- `section_id`
- `course_code`
- `course_name`
- `units`
- `hours_per_week`
- `sessions_per_week`
- `room_type`

**Optional columns:**
- `qualified_faculty`
- `priority`

## Screenshots
![Automatic-Scheduler 1](https://github.com/user-attachments/assets/10540cae-4f45-448d-9f2a-78a52488b465)
![Automatic-Scheduler 2](https://github.com/user-attachments/assets/03d964c1-e853-4716-9819-bdd067165f44)
![Automatic-Scheduler 3](https://github.com/user-attachments/assets/0cb82471-2b4f-48eb-94d3-58d37f0bf365)
![Automatic-Scheduler 4](https://github.com/user-attachments/assets/71673f0f-9af3-4e93-b8b2-65720939584f)


