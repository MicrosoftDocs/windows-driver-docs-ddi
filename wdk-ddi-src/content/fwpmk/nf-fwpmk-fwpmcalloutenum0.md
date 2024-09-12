---
UID: NF:fwpmk.FwpmCalloutEnum0
tech.root: netvista
title: FwpmCalloutEnum0
ms.date: 05/30/2024
targetos: Windows
description: The FwpmCalloutEnum0 function returns the next page of results from the callout enumerator.
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
 - FwpmCalloutEnum0
f1_keywords:
 - FwpmCalloutEnum0
 - fwpmk/FwpmCalloutEnum0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmCalloutEnum0
---

## -description

The **FwpmCalloutEnum0** function returns the next page of results from the callout enumerator.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumHandle [in]

Handle for a callout enumeration created by a call to **[FwpmCalloutCreateEnumHandle0](nf-fwpmk-fwpmcalloutcreateenumhandle0.md)**.

### -param numEntriesRequested [in]

The number of callout objects requested.

### -param entries [out]

Addresses of the enumeration entries.

### -param numEntriesReturned [out]

The number of callouts returned.

## -returns

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The callouts were enumerated successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the *numEntriesReturned* is less than the *numEntriesRequested*, the enumeration is exhausted.

The returned array of entries (but not the individual entries themselves) must be freed by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

A subsequent call using the same enumeration handle will return the next set of items following those in the last output buffer.

**FwpmCalloutEnum0** works on a snapshot of the callouts taken at the time the enumeration handle was created.

**FwpmCalloutEnum0** is a specific implementation of FwpmCalloutEnum. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmCalloutCreateEnumHandle0](nf-fwpmk-fwpmcalloutcreateenumhandle0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
