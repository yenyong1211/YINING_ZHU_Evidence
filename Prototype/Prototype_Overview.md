# AIRIS — Prototype Development

## Purpose and scope

AIRIS explores how home CCTV owners can understand data practices, locate privacy information and review shared viewing permissions. The project combines a third-party guidance concept with an eufy-inspired interface. It is a student design proposal, not an official eufy application or a confirmed manufacturer partnership.

This record describes the supplied local web project and my confirmed contribution. The connected AIRIS–eufy journey is described in the report and workflow; the local entry file currently redirects directly to `prototype/`. The third-party search implementation described in the root README is not included in this local folder.

## My contribution

I designed the Access History interface and viewing-permission states in Figma. This involved the screen layout, information hierarchy and interaction states for reviewing dates, expanding visits and inspecting what a shared viewer could see. In Week 12, I developed the Figma design into a web prototype, used an eufy-inspired interface context and created a shared GitHub repository for team integration. I also revised the prototype in the final stage, worked on the selected-product presentation and contributed to the report and promotional materials.

The complete project includes other members' modules. Inclusion in the shared repository does not mean that I independently authored every feature. AI assistance should be disclosed separately for the development and writing tasks in which it was used.

## Figma interaction design

[Open the Figma design](https://www.figma.com/design/VltMi5gQKe9sfibiUJXZUG/7380history)

| Design element | What the design explores | Why it matters |
| --- | --- | --- |
| Date selection | Today and earlier access records | Distinguishes when viewing occurred |
| Member cards | Viewer identity, role and visit count | Makes shared access easier to inspect |
| Expandable visits | Live viewing and recorded-video visits | Separates viewing behaviour from footage creation |
| Viewing permissions | A route from a member's record to their current visibility | Connects information with a possible action |
| Four visibility states | Original view, Hide faces, Hide whole person and No access | Makes the proposed options visible before a decision |
| Confirmation state | Feedback after a permission change | Helps explain the intended result and future-access scope |

These are interface and interaction design contributions. The illustrated states do not implement real video masking. The interviews motivate clearer access information, but do not establish that participants requested these exact four modes.

## Local web implementation

The inspected local source includes the following modules:

| File or directory | Role |
| --- | --- |
| `prototype/shell.js` | Shared interface context, navigation and native-style screens |
| `prototype/history/history.js` | Access History, viewing-permission interactions and routes |
| `prototype/history/data.js` | Seeded example people and visits |
| `prototype/products.js` | Selected-product catalogue and detail views |
| `prototype/privacy.js` | Privacy guides and basic information |
| `prototype/auth.js` | Simulated viewer-verification interaction |
| `agreement/` | Illustrated agreement and demo-entry screens |
| `docs/WORKFLOW.md` | Intended cross-platform workflow and remaining integration work |

### Access History and permissions

Access History is placed under Events, alongside Camera Events. It displays seeded visits and supports date and time filtering. Member cards can be expanded to show individual visits. Viewing permissions offer the four modes from the Figma design and store demonstration choices in browser storage where available.

Past visits and current permissions are separate. Changing a current permission does not remove historical visits or recover copies that a viewer might already have downloaded. The local history view reads seeded records; it should not be presented as a complete audit trail of real verification or viewing events.

### Selected products

The local catalogue contains eufyCam S3 Pro, Robot Vacuum Omni S1 Pro and Video Doorbell E340. These are product references within the demonstration. The robot vacuum is not presented as a live household surveillance feed. Earlier module documentation names other products; those names belong to an earlier development snapshot.

### Guidance and transition

The intended journey is: ask a privacy question, understand the explanation, find the relevant setting, review the options and choose. The workflow specifies page-by-page tutorials with highlighted targets and arrows. That tutorial design is a specification, not a feature verified in the supplied local code. Reading a guide should not silently accept terms or change a permission.

## Demonstration routes

These are route examples for the local project; the hosted deployment has not been checked here.

| Destination | Route |
| --- | --- |
| Home | `prototype/#home` |
| Camera Events | `prototype/#events` |
| Access History | `prototype/#events/access` |
| Emma's viewing permissions | `prototype/#events/permissions/emma` |
| James's viewing permissions | `prototype/#events/permissions/james` |
| Privacy guide | `prototype/#privacy` |
| Settings | `prototype/#settings` |

To inspect locally, serve the `cctv-prototype` folder using `python3 -m http.server 7380`, then open `http://localhost:7380/prototype/`.

## Limitations and reflection

The prototype does not connect to real cameras or authenticate a real eufy account. Browser-side permission changes and verification screens cannot establish production security. No real facial recognition, video anonymisation or deletion of household recordings is demonstrated.

Developing the web version helped me move beyond arranging screens towards explaining state changes and their consequences. The next evaluation should test whether users understand access records, future permission changes and the boundary between guidance and simulation. A clickable interface alone does not show that those explanations are understood.

## Supporting records

- [Privacy-label iterations](Privacy_Label_Iterations.md)
- [Proposed web evaluation tasks](Web_Evaluation_Tasks.md)
- [References](../References.md)

Source basis: local `cctv-prototype` code and documentation; A1.3 report Sections 3–5; the author's confirmed weekly contribution record.
