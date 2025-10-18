
---
### 🧩 Core idea

Design a parking system that supports:

- Entry/exit for vehicles
    
- Parking spot allocation & release
    
- Ticket generation & payment

## ✅ Key Entities

- **Vehicle**
    
- **Parking Spot**
    
- **Parking Floor / Level**
    
- **Ticket**
    
- **Payment**
    
- **SpotAllocationStrategy** (Strategy Pattern)
    
- **FeeCalculationStrategy** (Strategy Pattern)
    
- **ParkingManager** (Controller / Orchestrator)

## 🎯 Design Patterns Used

| Pattern               | Purpose                                                                                          |
| --------------------- | ------------------------------------------------------------------------------------------------ |
| **Strategy Pattern**  | For spot allocation (e.g., nearest-first, random) and fee calculation (e.g., hourly, flat rate). |
| **Singleton Pattern** | To manage single instance of `ParkingManager` for coordination.                                  |
| **Factory Pattern**   | To create `Vehicle` or `ParkingSpot` objects dynamically by type.                                |

## 🧱 Relationships

- One `ParkingFloor` → many `ParkingSpots`
    
- One `ParkingSpot` → 0 or 1 `Vehicle`
    
- One `Vehicle` → 0 or 1 `Ticket`
    
- One `Ticket` → 1 `Payment`
    
- `ParkingManager` uses `SpotAllocationStrategy` and `FeeCalculationStrategy`

