---
UID: NF:fwpmk.FwpmBfeStateUnsubscribeChanges0
title: FwpmBfeStateUnsubscribeChanges0 function (fwpmk.h)
description: The FwpmBfeStateUnsubscribeChanges0 function deregisters a base filtering engine (BFE) callback function that was previously registered by calling the FwpmBfeStateSubscribeChanges0 function.Note  FwpmBfeStateUnsubscribeChanges0 is a specific version of FwpmBfeStateUnsubscribeChanges. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpmbfestateunsubscribechanges0.htm
tech.root: netvista
ms.date: 06/21/2024
keywords: ["FwpmBfeStateUnsubscribeChanges0 function"]
ms.keywords: FwpmBfeStateUnsubscribeChanges0, FwpmBfeStateUnsubscribeChanges0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmBfeStateUnsubscribeChanges0, netvista.fwpmbfestateunsubscribechanges0, wfp_ref_2_funct_2_fwpm_2b1f650b-81ab-4dd9-be56-97039f86ac1e.xml
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
 - FwpmBfeStateUnsubscribeChanges0
 - fwpmk/FwpmBfeStateUnsubscribeChanges0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpmBfeStateUnsubscribeChanges0
---

# FwpmBfeStateUnsubscribeChanges0 function

## -description

The **FwpmBfeStateUnsubscribeChanges0** function deregisters a base filtering engine (BFE) callback function that was previously registered by calling the [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0) function.

> [!WARNING]
> Do not call **FwpmBfeStateUnsubscribeChanges0** from a callback function that your driver previously registered by calling [FwpmBfeStateSubscribeChanges0](nf-fwpmk-fwpmbfestatesubscribechanges0.md). Doing so can cause a deadlock.

## -parameters

### -param changeHandle [in, out]

A handle associated with the registration of the callback function that is being deregistered. This handle was returned to the callout driver when it called the [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0) function to register the callback function.

## -returns

The **FwpmBfeStateUnsubscribeChanges0** function returns one of the following NTSTATUS codes:

| Return code | Description |
| --- | --- |
| **STATUS_SUCCESS** | The callback function was successfully deregistered. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

A callout driver calls the **FwpmBfeStateUnsubscribeChanges0** function to deregister a callback function that was previously registered by calling the [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0) function.

If a callout driver registers a callback function by calling the [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0) function, it must deregister the callback function before the callout driver can be unloaded.

**FwpmBfeStateUnsubscribeChanges0** is a specific version of **FwpmBfeStateUnsubscribeChanges**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- [FwpmBfeStateSubscribeChanges0](/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmbfestatesubscribechanges0)
