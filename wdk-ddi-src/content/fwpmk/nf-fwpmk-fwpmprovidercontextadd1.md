---
UID: NF:fwpmk.FwpmProviderContextAdd1
tech.root: netvista
title: FwpmProviderContextAdd1
ms.date: 06/12/2024
targetos: Windows
description: The FwpmProviderContextAdd1 function adds a new provider context to the system.
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
 - FwpmProviderContextAdd1
f1_keywords:
 - FwpmProviderContextAdd1
 - fwpmk/FwpmProviderContextAdd1
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmProviderContextAdd1
---

## -description

The **FwpmProviderContextAdd1** function adds a new provider context to the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param providerContext [in]

The provider context object to be added.

### -param sd [in, optional]

Security information associated with the provider context object.

### -param id [out, optional]

Pointer to a variable that receives a runtime identifier for this provider context.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The provider context was successfully added. |
| **ERROR_NOT_SUPPORTED**<br>0x32 | The [FWPM_IPSEC_IKE_MM_CONTEXT](/windows/desktop/api/fwpmtypes/ne-fwpmtypes-fwpm_provider_context_type)and the [IKEEXT_IPV6_CGA](/windows/desktop/api/iketypes/ne-iketypes-ikeext_authentication_method_type) authentication method in the **authenticationMethods** array, but cryptographically generated address (CGA) is not enabled in the registry. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

Some fields in the [FWPM_PROVIDER_CONTEXT1](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_provider_context1) structure are assigned by the system, not the caller, and are ignored in the call to **FwpmProviderContextAdd1**.

If the caller supplies a **NULL** security descriptor, the system assigns a default security descriptor.

This function cannot be called from within a read-only transaction, it fails with **FWP_E_INCOMPATIBLE_TXN**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

The caller needs [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers) access to the provider context's container and **FWPM_ACTRL_ADD_LINK** access to the provider (if any). See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmProviderContextAdd0** is a specific implementation of **FwpmProviderContextAdd**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [FWPM_IPSEC_IKE_MM_CONTEXT](/windows/desktop/api/fwpmtypes/ne-fwpmtypes-fwpm_provider_context_type)
- [FWPM_PROVIDER_CONTEXT1](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_provider_context1)
- [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers)
- [IKEEXT_IPV6_CGA](/windows/desktop/api/iketypes/ne-iketypes-ikeext_authentication_method_type)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
