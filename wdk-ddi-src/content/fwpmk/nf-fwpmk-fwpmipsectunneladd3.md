---
UID: NF:fwpmk.FwpmIPsecTunnelAdd3
tech.root: netvista
title: FwpmIPsecTunnelAdd3
ms.date: 06/21/2024
targetos: Windows
description: The FwpmIPsecTunnelAdd3 function adds a new Internet Protocol Security (IPsec) tunnel mode policy to the system.
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
 - FwpmIPsecTunnelAdd3
f1_keywords:
 - FwpmIPsecTunnelAdd3
 - fwpmk/FwpmIPsecTunnelAdd3
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmIPsecTunnelAdd3
---

## -description

The **FwpmIPsecTunnelAdd3** function adds a new Internet Protocol Security (IPsec) tunnel mode policy to the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param flags [in]

Possible values:

| IPsec tunnel flag | Meaning |
|--|--|
| **FWPM_TUNNEL_FLAG_POINT_TO_POINT** | Adds a point-to-point tunnel to the system. |
| **FWPM_TUNNEL_FLAG_ENABLE_VIRTUAL_IF_TUNNELING** | Enables virtual interface-based IPsec tunnel mode. |

### -param mainModePolicy [in, optional]

An optional Main Mode policy for the IPsec tunnel.

### -param tunnelPolicy [in]

The Quick Mode policy for the IPsec tunnel.

### -param numFilterConditions [in]

The number of filter conditions present in *filterConditions*.

### -param filterConditions [in, reads(numFilterConditions)]

An array of filter conditions that describe the traffic that should be tunneled by IPsec.

### -param keyModKey [in, optional]

An optional pointer to a GUID that uniquely identifies the keying module key. If you supply this parameter, then only that keying module will be used for the tunnel. Otherwise, the default keying policy applies.

### -param sd [in, optional]

The security information associated with the IPsec tunnel.

## -returns

| Return code/value | Description |
|--|--|
| **ERROR_SUCCESS**<br>0 | The IPsec tunnel mode policy was successfully added. |
| **FWP_E_INVALID_PARAMETER**<br>0x80320035 | FWPM_TUNNEL_FLAG_POINT_TO_POINT wasn't set, and conditions other than local/remote address were specified. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP)-specific error. For details, see [WFP error codes](/windows/win32/fwp/wfp-error-codes). |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

You can't call this function within a read-only transaction, it fails with **FWP_E_INCOMPATIBLE_TXN**. For more info about transactions, see [Object Management](/windows/desktop/FWP/object-management).

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [WFP error codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
