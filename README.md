# Building Management System

A simple Python demo that models a building's core systems using an abstract base class and polymorphism. Each system implements a common interface, allowing them to be managed uniformly through a single loop.

## Overview

The program defines an abstract class `BuildingSystem` that specifies three required behaviors — `start()`, `stop()`, and `status()` — that every concrete building system must implement. This demonstrates the **Template/Interface pattern** using Python's `abc` module, ensuring all subclasses conform to a consistent contract.

## Structure

### Abstract Base Class

- **`BuildingSystem(ABC)`** — Defines three abstract methods that all subclasses must implement:
  - `start()` — Activates the system
  - `stop()` — Deactivates the system
  - `status()` — Reports the current state of the system

### Concrete Implementations

| Class | Description                                                       |
|---|-------------------------------------------------------------------|
| `AirConditioningSystem` | Manages climate control (start, stop, report temperature)         |
| `LightingSystem` | Manages auditorium lighting (on, off, brightness level)           |
| `SecuritySystem` | Manages motion detectors and cameras (arm, disarm, anomaly report) |
| `FireAlarmSystem` | Manages smoke detectors (activate, deactivate, detection status)  |

Each class overrides the three abstract methods with its own printed output describing the action taken.

## How It Works

1. An instance of each system is created and stored in a `systems` list.
2. The program iterates over the list, and for **each** system calls, in order:
   - `start()`
   - `stop()`
   - `status()`
3. Because every class inherits from the same abstract base, the loop can treat all systems interchangeably — this is polymorphism in action.

## Requirements

- Python 3.4+ (for the `abc` module)
- No external dependencies

### Example Output

```
The Air Conditioning System has been started:Climate Control Initiated
The Air Conditioning System has been stopped:Climate Control Deactivated
The Air Conditioning System is operating efficiently at a cool 22 degrees
The Lighting System has been started:Auditorium Lights Turned on
The Lighting System has been stopped:Auditorium Lights Turned off
The Lighting System are enabled at 60% brightness 
The Security System has been started:Motion Detectors and Cameras Activated
The Security System has been stopped:Motion Detectors and Cameras deactivated
The Security System has not detected any anomalies
The Fire Alarm System has been started:Smoke Detectors are now active
The Fire Alarm System has been stopped:Smoke Detectors are now dormant
The Fire Alarm System is now active, no smoke detected
```

## Extending the Project

To add a new building system (e.g., `ElevatorSystem`), create a class that:

1. Inherits from `BuildingSystem`
2. Implements `start()`, `stop()`, and `status()`
3. Gets added to the `systems` list

No changes to the main loop are required — this is the benefit of programming to an abstract interface.

# Author
Jezreel Andrews Tannoh  
EL 1B, Electrical and Electronic Engineering  
FOE.41.006.153.25