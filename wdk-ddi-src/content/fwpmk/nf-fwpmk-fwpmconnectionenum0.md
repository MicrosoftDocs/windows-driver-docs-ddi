---
UID: NF:fwpmk.FwpmConnectionEnum0
tech.root: netvista
title: FwpmConnectionEnum0
ms.date: 06/04/2024
targetos: Windows
description: The FwpmConnectionEnum0 function returns the next page of results from the connection object enumerator.
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
 - FwpmConnectionEnum0
f1_keywords:
 - FwpmConnectionEnum0
 - fwpmk/FwpmConnectionEnum0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmConnectionEnum0
---

## -description

The **FwpmConnectionEnum0** function returns the next page of results from the connection object enumerator.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumHandle [in]

Handle for a provider context enumeration created by a call to **[FwpmConnectionCreateEnumHandle0](nf-fwpmk-fwpmconnectioncreateenumhandle0.md)**.

### -param numEntriesRequested [in]

Number of connection objects requested.

### -param entries [out]

Addresses of enumeration entries.

### -param numEntriesReturned [out]

The number of entries returned in the *entries* parameter.

## -returns

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The connection objects were enumerated successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the *numEntriesReturned* is less than the *numEntriesRequested*, the enumeration is exhausted.

The returned array of entries (but not the individual entries themselves) must be freed by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

A subsequent call using the same enumeration handle will return the next set of items following those in the last output buffer.

**FwpmConnectionEnum0** works on a snapshot of the connection objects taken at the time the enumeration handle was created.

## -see-also

- **[FWPM_CONNECTION0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_connection0)**
- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmConnectionCreateEnumHandle0](nf-fwpmk-fwpmconnectioncreateenumhandle0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
