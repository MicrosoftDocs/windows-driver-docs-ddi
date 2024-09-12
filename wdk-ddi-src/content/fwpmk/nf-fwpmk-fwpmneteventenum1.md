---
UID: NF:fwpmk.FwpmNetEventEnum1
tech.root: netvista
title: FwpmNetEventEnum1
ms.date: 06/11/2024
targetos: Windows
description: The FwpmNetEventEnum1 function returns the next page of results from the network event enumerator.
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
 - FwpmNetEventEnum1
f1_keywords:
 - FwpmNetEventEnum1
 - fwpmk/FwpmNetEventEnum1
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmNetEventEnum1
---

## -description

The **FwpmNetEventEnum1** function returns the next page of results from the network event enumerator.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumHandle [in]

Handle for a network event enumeration created by a call to **[FwpmNetEventCreateEnumHandle0](nf-fwpmk-fwpmneteventcreateenumhandle0.md)**.

### -param numEntriesRequested [in]

The number of enumeration entries requested.

### -param entries [out]

Addresses of enumeration entries.

### -param numEntriesReturned [out]

The number of enumeration entries returned.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The network events were enumerated successfully. |
| **FWP_E_NET_EVENTS_DISABLED**<br>0x80320013 | The collection of network diagnostic events is disabled. Call **[FwpmEngineSetOption0](nf-fwpmk-fwpmenginesetoption0.md)** to enable it. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the *numEntriesReturned* is less than the *numEntriesRequested*, the enumeration is exhausted.

The returned array of entries (but not the individual entries themselves) must be freed by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

A subsequent call that uses the same *enumHandle* parameter returns the next set of events following those in the current *entries* buffer.

**FwpmNetEventEnum1** returns only events that were logged prior to the creation of the *enumHandle* parameter. See [Logging](/windows/desktop/FWP/logging) for more information.

**FwpmNetEventEnum1** is a specific implementation of **FwpmNetEventEnum**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- **[FwpmNetEventCreateEnumHandle0](nf-fwpmk-fwpmneteventcreateenumhandle0.md)**
- **[FwpmEngineSetOption0](nf-fwpmk-fwpmenginesetoption0.md)**
- **[FwpmNetEventCreateEnumHandle0](nf-fwpmk-fwpmneteventcreateenumhandle0.md)**
- [FWPM_NET_EVENT1](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_net_event1)
- [WFP Logging](/windows/desktop/FWP/logging)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
