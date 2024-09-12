---
UID: NF:fwpmk.FwpmSubLayerAdd0
tech.root: netvista
title: FwpmSubLayerAdd0
ms.date: 06/18/2024
targetos: Windows
description: The FwpmSubLayerAdd0 function adds a new sublayer to the system.
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
 - FwpmSubLayerAdd0
f1_keywords:
 - FwpmSubLayerAdd0
 - fwpmk/FwpmSubLayerAdd0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmSubLayerAdd0
---

## -description

The **FwpmSubLayerAdd0** function adds a new sublayer to the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param subLayer [in]

The sublayer to be added.

### -param sd [in, optional]

Security information for the sublayer object.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The sublayer was successfully added. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the caller supplies a **NULL** security descriptor, the system will assign a default security descriptor.

This function cannot be called from within a read-only transaction, it fails with **FWP_E_INCOMPATIBLE_TXN**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

The caller needs [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers) access to the sublayers's container and **FWPM_ACTRL_ADD_LINK** access to the provider (if any). See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmSubLayerAdd0** is a specific implementation of **FwpmSubLayerAdd**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers)
- [FWPM_SUBLAYER0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_sublayer0)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
- [Management Functions](/windows/desktop/FWP/fwp-mgmt-functions)
- [WFP Functions](/windows/desktop/FWP/fwp-functions)
