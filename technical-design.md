# Technical Design Document

## 1. Purpose
Describe a proposed IoT architecture for monitoring selected vehicle parameters and presenting status information to a user. This document describes the intended design; it does not certify that all components are implemented.

## 2. Requirements

### Functional requirements
- FR-1: The system should acquire readings from supported sensors.
- FR-2: The controller should validate readings and flag missing or out-of-range values.
- FR-3: The dashboard should display the latest received values and their timestamps.
- FR-4: Configured rules should flag low fuel, abnormal battery condition, high temperature, or overspeeding.
- FR-5: The system should indicate communication loss or stale data.
- FR-6: Alert delivery should be logged when a notification service is integrated.

### Non-functional requirements
- NFR-1: Protect vehicle electrical systems with suitable interface circuits and fusing.
- NFR-2: Keep credentials and API keys out of source control.
- NFR-3: Identify simulated values clearly.
- NFR-4: Make data timestamps and units visible.
- NFR-5: Validate reliability and latency before claiming real-time performance.

## 3. Proposed architecture
1. **Sensing layer:** selected fuel, battery, temperature, and speed sensors.
2. **Edge layer:** ESP32 or another suitable controller reads sensors, applies basic validation, and timestamps samples.
3. **Communication layer:** Wi-Fi or another suitable link transports data. The choice depends on vehicle connectivity and deployment constraints.
4. **Service layer:** optional broker/API/database authenticates devices and stores telemetry.
5. **Application layer:** dashboard displays values and alerts.
6. **Notification layer:** optional mobile/email/SMS service sends notifications according to configured rules.

## 4. Example data format
```json
{
  "device_id": "demo-vehicle-01",
  "timestamp": "2026-10-09T10:00:00Z",
  "fuel_percent": 42,
  "battery_voltage_v": 12.4,
  "engine_temperature_c": 84,
  "speed_kmh": 36,
  "source": "sample"
}
```
This is an illustrative schema only. Units, ranges, sensor calibration, and timestamps must be confirmed for the actual implementation.

## 5. Example alert rules
Thresholds below are examples for software testing, not universal vehicle service limits:
- Low fuel: fuel percentage below a configurable demo threshold.
- Temperature warning: temperature above a configurable demo threshold.
- Overspeed: speed above the configured demonstration speed limit.
- Battery warning: voltage outside a threshold established for the specific battery, operating state, and vehicle.
- Stale data: no new sample received within the configured timeout.

Actual thresholds must be chosen using the vehicle and sensor manufacturer's specifications.

## 6. Data flow
1. Sensor produces a measurement.
2. Controller reads and validates the measurement.
3. Controller timestamps the sample and sends it to the service.
4. Service authenticates the device and stores or forwards the sample.
5. Dashboard updates the visible status.
6. Alert logic evaluates configured rules and records any triggered alert.

## 7. Security and privacy
- Never commit Wi-Fi passwords, API keys, access tokens, or personal data.
- Use authenticated communication and access controls when connecting real devices.
- Collect only data needed for the project.
- Obtain consent before tracking a driver or sharing location data.
- Restrict access to location and driving-history data.

## 8. Safety and validation
- Do not connect an ESP32 GPIO directly to vehicle battery voltage or automotive signal lines.
- Use suitable protection, isolation, voltage conversion, and fusing.
- Bench-test sensor circuits before vehicle installation.
- Treat this project as an educational prototype, not as a replacement for factory safety systems or professional maintenance.
- Document the test setup, expected result, actual result, and pass/fail status.

## 9. Current implementation boundary
The repository includes a static HTML dashboard prototype. Live sensor acquisition, ESP32 firmware, backend storage, notification delivery, and vehicle integration require separate implementation and validation unless demonstrably present in the source.
