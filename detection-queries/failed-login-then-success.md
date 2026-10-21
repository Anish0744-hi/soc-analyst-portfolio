# Detection Rule: Successful Login After Repeated Failures

## Objective
Identify potentially suspicious authentication activity where multiple failed login attempts are followed by a successful login for the same user from the same source IP address.

## Detection Conditions
- At least 3 failed login attempts.
- Same username and source IP address.
- A successful login within 5 minutes of the failed attempts.

## Sample Security Logs

| Time | Username | Source IP | Result |
|---|---|---|---|
| 10:01:05 | alex | 198.51.100.24 | Failed |
| 10:01:15 | alex | 198.51.100.24 | Failed |
| 10:01:25 | alex | 198.51.100.24 | Failed |
| 10:01:35 | alex | 198.51.100.24 | Failed |
| 10:01:45 | alex | 198.51.100.24 | Success |

*These are fictional training events. The IP address belongs to a reserved documentation range.*

## Expected Result
Generate an alert because four failed attempts were followed by a successful login for the same user and source IP within 40 seconds.

## Possible False Positives
- A legitimate user repeatedly entering an incorrect password.
- A user successfully logging in after remembering the correct password.
- Automated systems retrying authentication with outdated credentials.

## Recommended Investigation
1. Check whether the source IP and device are familiar.
2. Review MFA results and authentication history.
3. Examine activity after the successful login.
4. Check for privilege changes or access to sensitive files.
5. Escalate according to the incident response procedure if suspicious evidence is found.

## Analyst Conclusion
The activity is suspicious and warrants investigation. The available events alone do not confirm account compromise.
## Test Cases

The following test cases use fictional login events to evaluate the detection logic. The threshold is at least three failed logins followed by a successful login within five minutes, using the same username and source IP.

| Test | Login activity | Expected result | Reason |
|---|---|---|---|
| 1 | Alex has 3 failures, then 1 success within 3 minutes from the same IP. | Alert | The threshold is met. |
| 2 | Sam has 2 failures, then 1 success within 2 minutes from the same IP. | No alert | Fewer than 3 failures. |
| 3 | Alex has 3 failures, then a success 10 minutes later. | No alert | The failures are outside the preceding 5-minute window. |
| 4 | Alex has 3 failures from one IP, then a success from a different IP. | No alert from this rule | The username and source IP do not both match. A separate detection could investigate this pattern. |

### Validation Status

These are manually reasoned test cases, not results from a live SIEM. The SPL query still needs to be tested against sample events in Splunk before being considered validated.

### Limitations

- Legitimate users who mistype passwords may trigger similar patterns.
- Shared networks, VPNs, and NAT can affect source-IP interpretation.
- A matching alert indicates suspicious activity, not confirmed account compromise.
- The time window and field names must be checked against the actual log source.
