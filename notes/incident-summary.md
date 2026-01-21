## Incident Summary

### Incident 1: SSH Access Failure
- Impact: Unable to access VM remotely
- Cause: Firewall deny rule blocking SSH
- Resolution: Removed deny rule
- Prevention: Review firewall changes before deployment

### Incident 2: IAM Permission Issue
- Impact: User access denied
- Cause: Missing Compute Engine IAM role
- Resolution: Assigned correct role
- Prevention: Apply least-privilege access policies
