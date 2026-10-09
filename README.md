# Smart Vehicle Monitoring and Safety System using IoT

**Project type:** Student / hackathon prototype  
**Domain:** Internet of Things (IoT), embedded systems, vehicle safety  
**Status:** Dashboard prototype; hardware integration and real-world testing are not yet verified.

## Overview
The Smart Vehicle Monitoring and Safety System is designed to help a vehicle owner monitor important vehicle parameters and identify potentially unsafe conditions. The proposed system uses an ESP32 microcontroller and sensors to collect vehicle data, with a dashboard for viewing readings and alerts.

The current `index.html` file is a browser-based dashboard prototype. Unless connected to real sensors or a backend, its displayed values and alerts should be treated as demonstration/simulated data.

## Objectives
- Demonstrate a dashboard for vehicle health and safety monitoring.
- Plan monitoring for fuel level, battery condition, engine temperature, and vehicle speed.
- Show how abnormal conditions could trigger user notifications.
- Support preventive maintenance and responsible driving.
- Provide a foundation for later GPS, accident detection, and emergency-notification features.

## Planned system flow
```text
Vehicle sensors
      |
      v
ESP32 / edge controller
      |
      v
Wi-Fi or other communication link
      |
      v
Data service / cloud (to be implemented)
      |
      v
Web or mobile dashboard + alerts
```

## Planned monitoring parameters

| Parameter | Possible input | Purpose |
|---|---|---|
| Fuel level | Fuel-level sensor | Notify when fuel is low |
| Battery condition | Voltage/current sensing circuit | Identify low battery voltage or abnormal behavior |
| Engine temperature | Suitable temperature sensor | Warn when temperature exceeds a configured threshold |
| Vehicle speed | Speed sensor / wheel sensor / GPS | Display speed and flag overspeeding |

Sensor selection and electrical interfaces must be validated for the actual vehicle before hardware deployment.

## Repository contents
- `index.html` — dashboard prototype.
- `docs/technical-design.md` — proposed architecture, components, data flow, and safety considerations.
- `data/sample_data.csv` — illustrative sample data (not real vehicle telemetry).
- `tests/test_cases.md` — manual test cases and expected behavior.
- `LICENSE` — MIT License.
- `.gitignore` — common files to exclude from version control.

## Run the prototype
1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Interact with the dashboard controls, if available.

No Python server or dependency installation is required for the static HTML prototype. Browser behavior may vary depending on features used by the page.

## Important limitations
- This repository contains a front-end prototype, not a certified vehicle safety product.
- Sensor readings, cloud connectivity, alert delivery, GPS tracking, and accident detection are not considered operational unless separately implemented and tested with hardware/services.
- Do not use the prototype to make real-world driving or maintenance decisions.
- Vehicle wiring and sensor integration should be performed by qualified personnel, with appropriate isolation and protection.

## Team
- Sriram AB
- Ajay T
- Shree Haris

## Future work
1. Select and calibrate sensors for the intended vehicle.
2. Implement ESP32 firmware and sensor validation.
3. Add a backend or IoT platform for secure telemetry.
4. Connect the dashboard to live data.
5. Implement notification rules and test alert delivery.
6. Add GPS / accident-alert functions only after safety and privacy review.

## Contribution
For a student project, proposed improvements can be documented through issues and pull requests. Please describe whether a feature is simulated or hardware-tested.

## License
This project is released under the MIT License. See `LICENSE`.
