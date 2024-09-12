---
UID: NF:fwpmk.FwpmProviderContextGetByKey3
tech.root: netvista
title: FwpmProviderContextGetByKey3
ms.date: 05/30/2024
targetos: Windows
description: The FwpmProviderContextGetByKey3 function retrieves a provider context.
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
 - FwpmProviderContextGetByKey3
f1_keywords:
 - FwpmProviderContextGetByKey3
 - fwpmk/FwpmProviderContextGetByKey3
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmProviderContextGetByKey3
---

## -description

The **FwpmProviderContextGetByKey3** function retrieves a provider context.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param key

Pointer to a GUID that uniquely identifies the provider context. This is a pointer to the same GUID that was specified when the application called **[FwpmProviderContextAdd3](nf-fwpmk-fwpmprovidercontextadd3.md)** for this object.

### -param providerContext

The provider context information.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The provider context was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller must free the returned object by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

The caller needs [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers) access to the provider context. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmProviderContextGetByKey0** is a specific implementation of **FwpmProviderContextGetByKey**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

Here are all the links in the current document:

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmProviderContextAdd3](nf-fwpmk-fwpmprovidercontextadd3.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers)
- [FWPM_PROVIDER_CONTEXT3](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_provider_context3)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
