# Failed Login Investigation

## 1. Objective
Investigate repeated failed login attempts followed by a successful login.

## 2. Sample Log Data

| Time | Username | Source IP | Result |
|---|---|---|---|
| 09:01:02 | admin | 203.0.113.25 | Failed |
| 09:01:05 | admin | 203.0.113.25 | Failed |
| 09:01:08 | admin | 203.0.113.25 | Failed |
| 09:01:12 | admin | 203.0.113.25 | Failed |
| 09:01:17 | admin | 203.0.113.25 | Failed |
| 09:02:01 | admin | 203.0.113.25 | Success |

## 3. Initial Findings
- Five failed login attempts occurred before a successful login.
- All attempts targeted the admin account.
- All attempts used the same source IP address.
- The pattern is suspicious and requires further investigation.

## 4. Analyst Assessment
**Preliminary verdict:** Suspicious authentication activity.

The logs alone do not prove that an account was compromised.

## 5. Recommended Next Steps
1. Verify whether the successful login was legitimate.
2. Review the successful session's activity.
3. Correlate with other authentication and endpoint logs.
4. Follow the organisation's incident-response procedure if compromise is suspected.

## 6. Data Limitation
The IP address 203.0.113.25 belongs to a documentation-only IP range. This is simulated training data, not evidence of a real attacker.

## 7. Skills Practised
- Authentication log analysis
- Suspicious login detection
- Evidence-based incident assessment
- Investigation documentation

---
*Training exercise using simulated data.*
