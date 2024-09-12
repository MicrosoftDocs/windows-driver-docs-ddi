---
UID: NF:fwpmk.FwpmCalloutGetByKey0
tech.root: netvista
title: FwpmCalloutGetByKey0
ms.date: 05/31/2024
targetos: Windows
description: The FwpmCalloutGetByKey0 function retrieves a callout by using the GUID key for the callout.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpmk.h
req.idl: 
req.include-header: 
req.irql: <= PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpmk.h
api_name:
 - FwpmCalloutGetByKey0
f1_keywords:
 - FwpmCalloutGetByKey0
 - fwpmk/FwpmCalloutGetByKey0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmCalloutGetByKey0
---

## -description

The **FwpmCalloutGetByKey0** function retrieves a callout by using the GUID key for the callout.

## -parameters

### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** function to open a session to the filter engine.

### -param key [in]

Unique identifier of the callout. This GUID was specified in the **calloutKey** member of the *callout* parameter when the application called **[FwpmCalloutAdd0](nf-fwpmk-fwpmcalloutadd0.md)** for this object.

### -param callout [out]

Information about the state associated with the callout.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The callout was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See WFP Error Codes for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller must free the returned object by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

The caller needs [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers) access to the callout. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmCalloutGetByKey0** is a specific implementation of **FwpmCalloutGetByKey**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmCalloutAdd0](nf-fwpmk-fwpmcalloutadd0.md)**
