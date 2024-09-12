---
UID: NF:fwpmk.FwpmProviderAdd0
tech.root: netvista
title: FwpmProviderAdd0
ms.date: 06/12/2024
targetos: Windows
description: The FwpmProviderAdd0 function adds a new provider to the system.
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
 - FwpmProviderAdd0
f1_keywords:
 - FwpmProviderAdd0
 - fwpmk/FwpmProviderAdd0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmProviderAdd0
---

## -description

The **FwpmProviderAdd0** function adds a new provider to the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param provider [in]

The provider object to be added.

### -param sd [in, optional]

Security information for the provider object.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The provider was successfully added. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the caller supplies a null security descriptor, the system will assign a default security descriptor.

Boot-time objects are added to the Base Filtering Engine (BFE) when the TCP/IP driver starts, and are removed once the BFE finishes initialization. Persistent objects are added when the BFE starts. If a policy provider has a persistent policy that is not intended to be enforced if its associated service is disabled, the caller can specify an optional service name in the [FWPM_PROVIDER0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_provider0) structure. This service then owns the persistent policy object. At start, the BFE only adds the following types of persistent objects to the system.

- The object is not associated with a provider.
- The object has an associated provider that does not specify a service name.
- The object has an associated provider and an associated service set to auto-start.

This function cannot be called from within a read-only transaction, it fails  with **FWP_E_INCOMPATIBLE_TXN**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

The caller needs [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers) access to the provider's container. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmProviderAdd0** is a specific implementation of **FwpmProviderAdd**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [FWPM_PROVIDER0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_provider0)
- [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
