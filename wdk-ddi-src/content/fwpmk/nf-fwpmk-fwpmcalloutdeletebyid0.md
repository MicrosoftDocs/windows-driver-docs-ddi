---
UID: NF:fwpmk.FwpmCalloutDeleteById0
title: FwpmCalloutDeleteById0 function (fwpmk.h)
description: The FwpmCalloutDeleteById0 function deletes a callout from the filter engine.Note  FwpmCalloutDeleteById0 is a specific version of FwpmCalloutDeleteById.
old-location: netvista\fwpmcalloutdeletebyid0.htm
tech.root: netvista
ms.date: 06/21/2024
keywords: ["FwpmCalloutDeleteById0 function"]
ms.keywords: FwpmCalloutDeleteById0, FwpmCalloutDeleteById0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmCalloutDeleteById0, netvista.fwpmcalloutdeletebyid0, wfp_ref_2_funct_2_fwpm_466376ac-f7a1-417e-9de8-9c3a7ff31404.xml
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpmCalloutDeleteById0
 - fwpmk/FwpmCalloutDeleteById0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpmCalloutDeleteById0
---

# FwpmCalloutDeleteById0 function

## -description

The **FwpmCalloutDeleteById0** function deletes a callout from the filter engine.

## -parameters

### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the **[FwpmEngineOpen0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0)** function to open a session to the filter engine.

### -param id [in]

The run-time identifier for the callout that is being deleted from the filter engine. This must be the run-time identifier that was returned when the callout driver called the [FwpmCalloutAdd0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutadd0) function to add the callout to the filter engine.

## -returns

The **FwpmCalloutDeleteById0** function returns one of the following NTSTATUS codes.

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | The callout was successfully deleted from the filter engine. |
| **STATUS_FWP_IN_USE** | One or more filters in the filter engine specify the callout for the filter's action. |
| **STATUS_FWP_CALLOUT_NOT_FOUND** | There is not a callout in the filter engine that matches the run-time identifier specified in the *id* parameter. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

A callout driver calls the **FwpmCalloutDeleteById0** function to delete a callout from the filter engine, using the run-time identifier to identify the callout to be deleted.

Callout drivers do not typically delete their callouts from the filter engine. In most situations, this is handled by a user-mode [Windows Filtering Platform](/windows/desktop/FWP/windows-filtering-platform-start-page) management application.

A callout can be deleted from the filter engine only if there are no filters in the filter engine that specify the callout for the filter's action.

**FwpmCalloutDeleteById0** is a specific version of **FwpmCalloutDeleteById**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- [FwpmCalloutAdd0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutadd0)
- [FwpmCalloutDeleteByKey0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebykey0)
- [FwpmEngineOpen0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0)
