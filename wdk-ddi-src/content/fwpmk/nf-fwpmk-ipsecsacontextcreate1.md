---
UID: NF:fwpmk.IPsecSaContextCreate1
tech.root: netvista
title: IPsecSaContextCreate1
ms.date: 06/20/2024
targetos: Windows
description: The IPsecSaContextCreate1 function creates an IPsec security association (SA) context.
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
 - IPsecSaContextCreate1
f1_keywords:
 - IPsecSaContextCreate1
 - fwpmk/IPsecSaContextCreate1
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecSaContextCreate1
---

## -description

The **IPsecSaContextCreate1** function creates an IPsec security association (SA) context.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param outboundTraffic [in]

The outbound traffic of the SA.

### -param virtualIfTunnelInfo [in, optional]

Details related to virtual interface tunneling.

### -param inboundFilterId [out, optional]

Optional filter identifier of the cached inbound filter corresponding to the *outboundTraffic* parameter specified by the caller. Base filtering engine (BFE) may cache the inbound filter identifier and return the cached value, if available. Caller must handle the case when BFE does not have a cached value, in which case this parameter will be set to 0.

### -param id [out]

The identifier of the IPsec SA context.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The IPsec SA context was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a transaction, it fails with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

This function cannot be called from within a dynamic session. The call fails with **FWP_E_DYNAMIC_SESSION_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about dynamic sessions.

The caller needs [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers) access to the IPsec security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IPsecSaContextCreate1** is a specific implementation of **IPsecSaContextCreate**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers)
- [IPSEC_TRAFFIC1](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_traffic0)
- [IPSEC_VIRTUAL_IF_TUNNEL_INFO0](/windows/desktop/api/fwptypes/ns-fwptypes-ipsec_virtual_if_tunnel_info0)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
