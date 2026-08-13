## Copilot instructions for Google Cloud NetApp Volumes documentation

### Repository overview
Product: Google Cloud NetApp Volumes in NetApp Console

This repository documents how to discover, view, and remove *Google Cloud NetApp Volumes* systems from the *NetApp Console*.
It covers required Google Cloud identity setup, NetApp Console role assignment, and system-level management workflows for Google Cloud projects and regions.

### Repository structure
- `./` – Primary AsciiDoc pages for concepts, setup, role assignment, system discovery, volume management, support, and legal notices.
- `_whatsnew/` – Date-based release-note include files referenced by `whats-new.adoc`.
- `store-redirects/` – Redirect-only AsciiDoc stubs mapping retired page permalinks to current task pages.
- `media/` – UI screenshots and icons used by task and concept pages.
- `_include/` – Reserved include-content folder; currently a placeholder directory for future local include files.

### Product-specific context
**Architecture and components:**
- *NetApp Console* is the management interface where users add a *Google Cloud NetApp Volumes system* and then enter that system to view volumes and audit logs.
- *Google Cloud* provides the project, region, IAM roles, and service account context used to discover volumes in NetApp Console.
- Discovery uses a customer service account plus NetApp-owned service account impersonation to obtain short-lived access tokens instead of private-key sharing.
- A discovered system represents subscription/project context in NetApp Console; removing the system detaches visibility in NetApp Console but does not delete Google Cloud NetApp Volumes resources.

**Key concepts:**
- A *system* is the NetApp Console representation of Google Cloud NetApp Volumes resources for a selected project and region.
- *Service account setup* includes creating or selecting a Google Cloud service account, assigning Google Cloud NetApp Volumes IAM access, and granting impersonation permissions.
- *Shared VPC* scenarios require IAM role binding in each additional host project that uses the service account.
- *Timeline/Audit logs* in NetApp Console show actions performed on managed volumes.

**Naming conventions and terminology:**
- Use the product name *Google Cloud NetApp Volumes*; the repository also uses *GCNV* as shorthand in metadata and keywords.
- Use *NetApp Console* for the management UI terms, including navigation labels such as *Storage*, *Management*, *Add System*, and *Discover*.
- Role names used in tasks are *Google Cloud NetApp Volumes admin* and *Google Cloud NetApp Volumes viewer* (some existing content may omit “Volumes” in the viewer role name; prefer the full names above).
- Google identity terms used in tasks include *service account*, *IAM policy binding*, *service account impersonation*, *project name*, *region*, and *Shared VPC host project*.

### Typical user workflows
**Initial onboarding:** Learn product basics → Set up Google Cloud service account and IAM access → Assign NetApp Console application roles → Add/discover a Google Cloud NetApp Volumes system

**Operate existing storage view:** Open discovered system → Search and inspect volumes → View labels and capacity/region details → Review timeline audit logs

**Remove from NetApp Console scope:** Open system → Use system action menu → Remove system from NetApp Console → Re-discover later if needed
