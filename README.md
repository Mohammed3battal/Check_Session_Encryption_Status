## Script: Check SQL Server Session Encryption Status

**Description**:
This script queries the `sys.dm_exec_connections` DMV to check whether each active SQL Server connection is **encrypted**. It provides visibility into session-level encryption settings, which can help validate SSL/TLS usage and compliance with security policies.

**What It Shows**:
- `Session ID`: ID of the connection
- `Encrypted?`: Whether the session is encrypted (`TRUE` / `FALSE` / `NULL`)

**Use Case**:
- Verify if client applications are using encrypted connections
- Validate that SQL Server is enforcing encryption (if configured)
- Perform security audits to detect unencrypted sessions

**Requirements**:
- SQL Server 2005 or later
- `VIEW SERVER STATE` permission

**Notes**:
- `encrypt_option` returns:
  - `TRUE`: Encrypted
  - `FALSE`: Not encrypted
  - `NULL`: Internal or special connections
- Combine with `host_name`, `program_name`, or `client_net_address` if needed for more context.
