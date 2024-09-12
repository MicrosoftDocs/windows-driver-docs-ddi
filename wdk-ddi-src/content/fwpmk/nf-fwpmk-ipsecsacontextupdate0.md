---
UID: NF:fwpmk.IPsecSaContextUpdate0
tech.root: netvista
title: IPsecSaContextUpdate0
ms.date: 06/20/2024
targetos: Windows
description: The IPsecSaContextUpdate0 function updates an IPsec security association (SA) context.
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
 - IPsecSaContextUpdate0
f1_keywords:
 - IPsecSaContextUpdate0
 - fwpmk/IPsecSaContextUpdate0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecSaContextUpdate0
---

## -description

The **IPsecSaContextUpdate0** function updates an IPsec security association (SA) context.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param flags [in]

Flags indicating the specific field in the IPSEC_SA_CONTEXT1 structure that is being updated.

Possible values:

| IPsec SA flag | Meaning |
|--|--|
| **IPSEC_SA_DETAILS_UPDATE_TRAFFIC** | Updates the [IPSEC_SA_DETAILS1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_details1) structure. |
| **IPSEC_SA_DETAILS_UPDATE_UDP_ENCAPSULATION** | Updates the [IPSEC_SA_DETAILS1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_details1) structure. |
| **IPSEC_SA_BUNDLE_UPDATE_FLAGS** | Updates the [IPSEC_SA_BUNDLE1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_bundle1) structure. |
| **IPSEC_SA_BUNDLE_UPDATE_NAP_CONTEXT** | Updates the [IPSEC_SA_BUNDLE1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_bundle1) structure. |
| **IPSEC_SA_BUNDLE_UPDATE_KEY_MODULE_STATE** | Updates the [IPSEC_SA_BUNDLE1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_bundle1) structure. |
| **IPSEC_SA_BUNDLE_UPDATE_PEER_V4_PRIVATE_ADDRESS** | Updates the [IPSEC_SA_BUNDLE1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_bundle1) structure. |
| **IPSEC_SA_BUNDLE_UPDATE_MM_SA_ID** | Updates the [IPSEC_SA_BUNDLE1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_bundle1) structure. |

### -param newValues [in]

An inbound and outbound SA pair.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The IPsec SA context was updated successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

**IPsecSaContextUpdate0** is a specific implementation of **IPsecSaContextUpdate**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [IPSEC_SA_CONTEXT1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_context1)
- [IPSEC_SA_DETAILS1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_details1)
- [IPSEC_SA_BUNDLE1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_bundle1)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
