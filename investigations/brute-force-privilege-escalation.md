# Brute-Force and Privilege Escalation Investigation

## 1. Objective

Investigate a simulated authentication alert involving repeated failed logins, a subsequent successful login, and an unexpected administrator privilege change.

## 2. Simulated Evidence

| Time | Event | Observation |
|---|---|---|
| 09:40:01 | Failed authentication | Eight failed login attempts against `john` within five minutes |
| 09:41:10 | MFA denied | The employee rejected an authentication request |
| 09:42:03 | Privilege change | `john` was added to the Administrators group |

**Note:** These are fictional training events, not evidence from a real environment.

## 3. Investigation Findings

- Repeated login failures may indicate password guessing or repeated user errors.
- An MFA denial may indicate that an unexpected authentication request reached the account owner.
- An administrator privilege change can significantly increase the account's access.
- The combination of these events warrants further investigation.

## 4. Initial Assessment

**Priority:** High — provisional assessment

**Potential incident:** Account compromise or unauthorized privilege escalation.

The available evidence is suspicious but does not independently confirm that an attacker gained control of the account.

## 5. Recommended Actions

1. Preserve relevant authentication, MFA, and account-management logs.
2. Verify whether the privilege change was authorized.
3. Review successful login details, source IP, device history, and MFA records.
4. Investigate activity after the privilege change, including new accounts and access to sensitive resources.
5. Escalate to the incident-response team and follow approved containment procedures.
6. Document the final disposition and evidence supporting the conclusion.

## 6. Limitations

- The events are simulated and have not been collected from a real SIEM.
- The cause of the failed logins has not been confirmed.
- The MFA denial does not prove that MFA was bypassed.
- The authorization status of the privilege change is unknown.
- No live SPL query or detection rule has been validated against these events.

## 7. Conclusion

The event sequence is consistent with a potentially serious security incident. The appropriate next step is to preserve evidence, verify authorization, investigate related activity, and escalate according to incident-response procedures.

**Project status:** Training investigation documented; live validation pending.
