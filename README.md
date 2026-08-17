# SAP Agent Plugins

An [Agent Plugins](https://github.com/agentplugins/agent-plugins-spec) v1.0.0
package bundling the 18 Agent Skills from
[likweitan/abap-skills](https://github.com/likweitan/abap-skills) for SAP ABAP
development — RAP, CDS, OData, ABAP Cloud, testing, authorization, eventing,
migration, abapGit, and BTP diagram generation.

All skill content, scripts, and reference files are copied unmodified from the
upstream repository; only the plugin packaging (`plugin.json` manifest at the
package root) was added to conform to the Agent Plugins standard layout
(§4.2). See [LICENSE](./LICENSE) (MIT, © Lik Wei) for the original license,
preserved as required for redistribution.

## Layout

```text
sap-plugins/
├── plugin.json
├── mcp.json
├── LICENSE
└── skills/
    ├── abap/
    ├── abap-cloud/
    ├── abap-cloud-migration/
    ├── abap-sql-amdp/
    ├── abap-unit-testing/
    ├── abapgit/
    ├── atc-cloudification/
    ├── authorization-iam/
    ├── badi-enhancement/
    ├── btp-abap-environment/
    ├── btp-diagram-generator/
    ├── cds-view-entities/
    ├── clean-abap/
    ├── odata/
    ├── rap/
    ├── rap-business-events/
    ├── released-abap-classes/
    └── sap-fiori-url-generator/
```

A client conforming to the Agent Plugins specification discovers this package
by reading `plugin.json` at the root, then scanning `skills/` for
subdirectories containing `SKILL.md`, and reading `mcp.json` for MCP server
configuration.

## MCP servers

| Server            | Transport                                   | Purpose                                                                                                                      |
| ----------------- | ------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `chrome-devtools` | stdio (`npx -y chrome-devtools-mcp@latest`) | Chrome DevTools automation and inspection, used by the `btp-diagram-generator` skill's browser-based workflows               |
| `drawio`          | streamable-http (`https://mcp.draw.io/mcp`) | draw.io diagram generation/editing, used by the `btp-diagram-generator` skill to open and validate generated `.drawio` files |

## Skills

| Skill directory           | Purpose                                                                     |
| ------------------------- | --------------------------------------------------------------------------- |
| `abap`                    | abaplint + Clean ABAP static analysis and code quality review               |
| `abap-cloud`              | 3-tier extensibility model, ABAP Cloud restrictions, wrapper patterns       |
| `abap-cloud-migration`    | Cloud Readiness assessment, unreleased API replacement, migration workflow  |
| `abap-sql-amdp`           | Modern ABAP SQL (window functions, CTEs) and AMDP                           |
| `abap-unit-testing`       | Test classes, assertions, test doubles, CDS/SQL/RAP test environments       |
| `abapgit`                 | Repository setup, clone/push/pull, `.abapgit.xml`, branching, CI/CD         |
| `atc-cloudification`      | ATC Cloud Readiness / Clean Core checks via the Cloudification Repository   |
| `authorization-iam`       | Authorization objects, CDS access control (DCL), IAM apps, PFCG roles       |
| `badi-enhancement`        | BAdIs, fallback classes, enhancement spots, key user extensibility          |
| `btp-abap-environment`    | BTP ABAP Environment (Steampunk) setup, ADT connectivity, comm arrangements |
| `btp-diagram-generator`   | Generate SAP BTP solution architecture diagrams as draw.io files            |
| `cds-view-entities`       | CDS view entity modeling, annotations, associations, access controls        |
| `clean-abap`              | Clean ABAP style guide review across 15 categories                          |
| `odata`                   | RAP-based (V4/V2) and SEGW-based OData service development                  |
| `rap`                     | RAP behavior definitions, EML, managed/unmanaged BOs, draft handling        |
| `rap-business-events`     | RAP business events and SAP Event Mesh enterprise eventing                  |
| `released-abap-classes`   | Catalog of released ABAP Cloud classes with usage examples                  |
| `sap-fiori-url-generator` | Generate SAP Fiori Launchpad (FLP) URLs from the Fiori Apps Library         |

## Source

- Upstream: https://github.com/likweitan/abap-skills
- Agent Plugins Specification: https://github.com/agentplugins/agent-plugins-spec
