# PLC 100 Challenge

> 100 industrial control problems. 100 ladder logic solutions. 3 PLC ecosystems.

**PLC 100 Challenge** is an open-source, 100-day practice project focused on solving progressively more realistic PLC programming problems using **Ladder Diagram (LD)** across three major industrial automation platforms:

- **Omron CX-Programmer**
- **Mitsubishi GX Works**
- **Siemens TIA Portal**

The goal is not to memorize vendor-specific instructions. The goal is to understand the control logic well enough to implement the same automation problem across different PLC ecosystems.

---

## Why This Project Exists

PLC programming is easiest to learn through repeated problem solving.

Reading documentation explains individual instructions, but real competence comes from combining contacts, coils, timers, counters, interlocks, sequences, alarms, state logic, and process conditions into a complete control system.

This repository documents a **100-problem learning journey** designed to strengthen:

- Ladder logic fundamentals
- Boolean and sequential control
- Timers and counters
- Interlocking and permissive logic
- Motor and actuator control
- Sensor-based automation
- Alarm and fault handling
- Manual and automatic operating modes
- Sequence control
- Industrial control problem decomposition
- Cross-platform PLC programming
- Vendor-independent automation thinking

---

## Challenge Objective

Complete **100 PLC problems in 100 days**.

Each challenge starts from the same control requirement and is then implemented independently in:

1. **CX-Programmer**
2. **GX Works**
3. **TIA Portal**

The logic should remain functionally equivalent even when PLC addressing, instructions, memory areas, timer behavior, or programming conventions differ between platforms.

---

## Challenge Structure

The 100 problems are organized progressively.

| Level | Problems | Focus |
|---|---:|---|
| Fundamentals | 001–020 | Contacts, coils, latching, Boolean logic, timers, counters |
| Machine Control | 021–040 | Motors, sensors, actuators, interlocks, permissives |
| Sequence Control | 041–060 | Multi-step processes, state logic, automatic cycles |
| Industrial Logic | 061–080 | Alarms, fault handling, modes, process coordination |
| Integrated Systems | 081–100 | Larger machine and process automation scenarios |

The exact problem sequence may evolve as the repository grows.

---

## Repository Structure

```text
plc-100-challenge/
│
├── README.md
├── LICENSE
├── CONTRIBUTING.md
│
├── challenges/
│   ├── 001-start-stop-motor/
│   │   ├── README.md
│   │   ├── cx-programmer/
│   │   ├── gx-works/
│   │   ├── tia-portal/
│   │   └── assets/
│   │
│   ├── 002-forward-reverse-motor/
│   ├── 003-on-delay-control/
│   └── ...
│
└── docs/
    ├── conventions.md
    ├── platform-notes.md
    └── progress.md
```

Each challenge should contain a short technical explanation, I/O definition, expected behavior, ladder implementation, and verification notes.

---

## Recommended Challenge Format

Every problem should follow a consistent structure.

```text
Challenge XX — Title

Objective
Describe the control problem.

Inputs
List field inputs and logical conditions.

Outputs
List controlled outputs.

Control Requirements
Define the expected machine behavior.

Safety / Interlocks
Describe logical protections and prohibited states.

Sequence
Describe the operating sequence when applicable.

CX-Programmer
Implementation notes and project files.

GX Works
Implementation notes and project files.

TIA Portal
Implementation notes and project files.

Verification
Explain how the solution was tested.

Key Learning
Summarize the control concept demonstrated.
```

---

## Example Challenge

### Challenge 001 — Start/Stop Motor with Seal-In Logic

**Objective**

Create a motor control circuit where:

- Pressing `START` turns the motor ON.
- The motor remains ON after the START pushbutton is released.
- Pressing `STOP` turns the motor OFF.
- STOP has logical priority over START.

**Concepts**

- Normally open contact
- Normally closed contact
- Output coil
- Self-holding / seal-in circuit
- Basic industrial motor control logic

Equivalent ladder logic is then implemented separately in CX-Programmer, GX Works, and TIA Portal.

---

## Cross-Platform Philosophy

This repository intentionally separates the **control problem** from the **PLC implementation**.

For example, one platform may use different:

- Input/output addressing
- Internal relay areas
- Timer syntax
- Counter syntax
- Set/reset instructions
- Data registers
- Edge detection instructions
- Function block conventions

The engineering requirement, however, remains the same.

The challenge therefore trains the ability to think in terms of:

```text
Process Requirement
        ↓
Control Philosophy
        ↓
Boolean / Sequential Logic
        ↓
PLC Implementation
        ↓
Verification
```

rather than memorizing a single vendor's instruction set.

---

## Platforms

### Omron CX-Programmer

Primary focus:

- Omron PLC ladder programming
- CIO / Work / Data Memory usage
- TIM / CNT instructions
- Internal relay logic
- Basic sequence control

### Mitsubishi GX Works

Primary focus:

- Mitsubishi PLC ladder logic
- X / Y / M / D devices
- Timers and counters
- Internal relay logic
- Sequence implementation

### Siemens TIA Portal

Primary focus:

- Siemens PLC programming
- Inputs, outputs, memory, and DB-based variables
- IEC timers
- Structured tag usage
- Industrial program organization

---

## Progress

| Challenge | Topic | CX | GX | TIA |
|---|---|:---:|:---:|:---:|
| 001 | Start/Stop Motor | ☐ | ☐ | ☐ |
| 002 | Forward/Reverse Motor | ☐ | ☐ | ☐ |
| 003 | ON-Delay Control | ☐ | ☐ | ☐ |
| 004 | OFF-Delay Control | ☐ | ☐ | ☐ |
| 005 | Counter-Based Stop | ☐ | ☐ | ☐ |
| ... | ... | ... | ... | ... |
| 100 | Final Integrated Challenge | ☐ | ☐ | ☐ |

Progress is updated as challenges are completed.

---

## Engineering Principles

Solutions in this repository aim to follow several practical control-engineering principles:

- Fail-safe logic where applicable
- Clear separation between command and output logic
- Explicit interlocks
- Deterministic sequence behavior
- Readable rung organization
- Consistent tag naming
- Minimal unnecessary latching
- Safe reset behavior
- Documented assumptions
- Vendor-neutral reasoning before implementation

A working ladder program is not automatically a good industrial control program. Readability, maintainability, predictable behavior, and fault handling matter as well.

---

## Contribution

Contributions are welcome.

You can contribute by:

- Proposing new PLC challenges
- Improving existing ladder logic
- Adding alternative solutions
- Reviewing control sequences
- Improving documentation
- Adding simulation or test cases
- Porting a challenge to another PLC platform

Recommended contribution workflow:

```bash
git clone https://github.com/<username>/plc-100-challenge.git
cd plc-100-challenge

git checkout -b challenge/improve-xxx
git add .
git commit -m "Improve Challenge XXX"
git push origin challenge/improve-xxx
```

Then open a pull request describing:

- What was changed
- Why the change is needed
- Which PLC platform is affected
- How the logic was verified

---

## Open-Source Scope

The original challenge descriptions, documentation, diagrams, and user-created logic in this repository are intended to be open source under the repository license.

Vendor software such as CX-Programmer, GX Works, and TIA Portal remains the property of its respective owner and is **not distributed by this repository**.

Some PLC project files may require the corresponding proprietary engineering software to open.

---

## License

This project is released under the **MIT License** unless otherwise specified.

You are free to use, modify, study, and redistribute the original materials in this repository in accordance with the license.

See [`LICENSE`](LICENSE) for details.

---

## Disclaimer

This repository is intended for education, simulation, and engineering practice.

PLC logic used on real industrial machinery must undergo appropriate engineering review, risk assessment, safety validation, commissioning, and compliance checks before deployment.

Do not use educational ladder logic as a substitute for machine safety systems or certified safety PLC functions.

---

## Repository Goal

By Challenge 100, the target is not simply to have written 100 ladder programs.

The target is to be able to receive an automation requirement, break it into deterministic control logic, identify interlocks and failure conditions, implement the solution across different PLC ecosystems, and explain why the system behaves correctly.

**Learn the logic. Understand the machine. Then choose the PLC.**
