# SOC Incident Report: Suspicious Login and Possible Account Compromise

## 1. Incident Overview

- **Incident ID:** SOC-001
- **Incident type:** Suspicious authentication / possible account compromise
- **Initial severity:** High (provisional)
- **Status:** Under investigation
- **Environment:** Simulated training environment
- **Detection source:** Authentication and activity logs

## 2. Executive Summary

Five failed login attempts against the `admin` account were followed by a successful login. In this hypothetical scenario, a new account was subsequently created and a sensitive file was accessed.

The sequence raises concern about possible unauthorised access and persistence. Further investigation is required to establish whether the events are related, whether the actions were authorised, and whether sensitive information was transferred.

## 3. Timeline of Events

| Time | Event | Significance |
|---|---|---|
| 09:01:02–09:01:17 | Five failed login attempts | Possible password guessing |
| 09:02:01 | Successful login | Access may have been obtained |
| 09:03:10 | New account created | Possible unauthorised persistence |
| 09:04:22 | Sensitive file accessed | Potential data exposure |

*The last two events are hypothetical additions to the original training logs.*

## 4. Evidence and Findings

### Observed
- Five failed attempts targeted the `admin` account.
- A successful login followed the failures.
- In the scenario, a new account was created and a sensitive file was accessed.

### Assessment
- The activity may indicate password guessing followed by unauthorised access.
- The new account may have been created to maintain access.
- Sensitive information may have been exposed.

### Not yet confirmed
- Whether the login was unauthorised.
- Whether all events were performed by the same actor.
- Whether the new account was malicious.
- Whether data was copied or exfiltrated.

## 5. Recommended Response Actions

1. Escalate promptly under the organisation's incident-response procedure.
2. Preserve relevant authentication, endpoint, account-management, and file-access logs.
3. Verify the login with the account owner and check device, session, and source information.
4. Determine who created the new account and whether the action was approved.
5. Review file-access records and network telemetry for possible data transfer.
6. Apply proportionate containment measures if compromise is substantiated or the risk warrants urgent action, following authorised procedures.

## 6. Initial Verdict

**High-priority suspicious incident — investigation ongoing.**

The available scenario supports further investigation and escalation, but does not establish a confirmed compromise or data exfiltration.

## 7. Investigation Limitations

The exercise uses simulated data. The source IP `203.0.113.25` belongs to a documentation-only address range and should not be treated as a real attacker indicator.

## 8. Skills Practised

- Authentication log analysis
- Event correlation
- Incident severity assessment
- Evidence-based reporting
- Incident response recommendations

---
*Educational exercise. No real incident or victim is represented.*
