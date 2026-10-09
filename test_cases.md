# Test Cases

These are planned/manual tests for the prototype and future IoT implementation. Mark a test **Pass** only after performing it and recording evidence.

| ID | Test | Procedure | Expected result | Status |
|---|---|---|---|---|
| TC-01 | Dashboard opens | Open `index.html` in a modern browser | Page loads without a fatal error | Not run |
| TC-02 | Layout check | Check dashboard on desktop and mobile widths | Content remains readable and controls usable | Not run |
| TC-03 | Sample values identified | Review displayed values and documentation | Simulated/sample values are not misrepresented as live telemetry | Not run |
| TC-04 | Low-fuel rule | Feed a test fuel value below the configured demo threshold | Low-fuel warning is raised | Pending implementation |
| TC-05 | Temperature rule | Feed a test temperature above the configured demo threshold | Temperature warning is raised | Pending implementation |
| TC-06 | Overspeed rule | Feed a test speed above the configured demo limit | Overspeed warning is raised | Pending implementation |
| TC-07 | Missing data | Stop sending test telemetry | Dashboard indicates stale/offline data after timeout | Pending implementation |
| TC-08 | Invalid data | Send a missing, malformed, or out-of-range field | Data is rejected or clearly flagged | Pending implementation |
| TC-09 | Credentials handling | Search tracked files for secrets | No passwords or API keys are committed | Not run |
| TC-10 | Alert delivery | Trigger a test rule with notification service configured | Test alert is received and logged | Pending implementation |

## Test record template
- Test ID:
- Date/time:
- Browser / device / firmware version:
- Input or setup:
- Expected result:
- Actual result:
- Pass / Fail:
- Evidence link or screenshot:
- Notes:

**Safety note:** Do not deliberately create unsafe conditions while driving. Use simulated inputs or a controlled bench setup.
