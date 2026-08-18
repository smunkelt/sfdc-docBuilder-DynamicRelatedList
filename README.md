## Dynamic Related List

A configurable related-list component for Service Document templates that renders records dynamically using a relationship definition, optional source-link field path, configurable columns, sorting, and filter criteria. It includes built-in loading, empty, and error states, and formats Date/Time/DateTime values for user locale and timezone to improve readability in generated documents.

**Supported targets:** Service Document

### Artifacts

| Artifact | Type | API Name |
| --- | --- | --- |
| Component | LWC | `sfdcsm_DynamicRelatedList` |
| Controller | Apex Class | `sfdcsm_DBDynamicRelatedListController` |
| Test Class | Apex Class | `sfdcsm_DBDynamicRelatedListControllerTest` |

### Design Settings

| Setting | Purpose | Example |
| --- | --- | --- |
| `relatedEntityDefinition` | Target object + lookup field used to link related records. Format: `ChildObjectApiName:LookupFieldApiName`. | `WorkOrderLineItem:WorkOrderId` |
| `sourceLinkFieldPath` | Optional field path on the current record used as the linkage value. Defaults to current record Id when blank. | `SFS_WorkOrder__c` |
| `relatedListTitle` | Header text shown above the datatable. | `Installed Assets` |
| `titleSize` | Title text size: `standard`, `small`, `medium`, `large`. | `standard` |
| `showWhenEmpty` | When checked, shows title and empty-state message even if no related records are found. | `true` |
| `columnsToDisplay` | Comma-separated field API names to display. Supports relationship paths. | `Asset.Name,Asset.Product2.Name` |
| `columnLabels` | Comma-separated display labels matching column order. Defaults to field names if blank. | `Asset,Product` |
| `columnAlignments` | Comma-separated alignments per column: `left`, `center`, `right`. | `left,center` |
| `sortField` | Field API name used for sorting. Supports relationship field paths. | `LineItemNumber` |
| `sortOrder` | Sort direction: `ASC` or `DESC`. | `ASC` |
| `filterCriteria` | Additional SOQL WHERE criteria (without `WHERE`). | `Status = 'New'` |

Full documentation: [`documentation/sfdcsm_dynamicRelatedList-documentation.html`](./documentation/sfdcsm_dynamicRelatedList-documentation.html)

### Origin

Extracted from [smunkelt/sfdc-smunkelt](https://github.com/smunkelt/sfdc-smunkelt) into its own dedicated project/repository.

### Local Development

```bash
npm install
npm run test:unit
npm run lint
```
