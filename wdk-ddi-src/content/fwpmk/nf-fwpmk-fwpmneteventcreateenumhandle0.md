---
UID: NF:fwpmk.FwpmNetEventCreateEnumHandle0
tech.root: netvista
title: FwpmNetEventCreateEnumHandle0
ms.date: 06/11/2024
targetos: Windows
description: The FwpmNetEventCreateEnumHandle0 function creates a handle used to enumerate a set of network events.
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
 - FwpmNetEventCreateEnumHandle0
f1_keywords:
 - FwpmNetEventCreateEnumHandle0
 - fwpmk/FwpmNetEventCreateEnumHandle0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmNetEventCreateEnumHandle0
---

## -description

The **FwpmNetEventCreateEnumHandle0** function creates a handle used to enumerate a set of network events.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumTemplate [in, optional]

Template to selectively restrict the enumeration.

### -param enumHandle [out]

The handle for network event enumeration.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The enumerator was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If *enumTemplate* is **NULL**, all network event objects are returned.

The caller must call **[FwpmNetEventDestroyEnumHandle0](nf-fwpmk-fwpmneteventdestroyenumhandle0.md)** to free the returned handle.

This function cannot be called from within a transaction, it fails with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

The caller needs [FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers) access to the events' containers. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmNetEventCreateEnumHandle0** is a specific implementation of **FwpmNetEventCreateEnumHandle**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FWPM_NET_EVENT_ENUM_TEMPLATE0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_net_event_enum_template0)**
- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmNetEventDestroyEnumHandle0](nf-fwpmk-fwpmneteventdestroyenumhandle0.md)**
- [FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
