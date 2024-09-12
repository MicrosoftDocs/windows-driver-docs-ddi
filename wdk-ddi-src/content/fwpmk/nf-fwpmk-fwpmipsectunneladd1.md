---
UID: NF:fwpmk.FwpmIPsecTunnelAdd1
tech.root: netvista
title: FwpmIPsecTunnelAdd1
ms.date: 06/07/2024
targetos: Windows
description: The FwpmIPsecTunnelAdd1 function adds a new Internet Protocol Security (IPsec) tunnel mode policy to the system.
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
 - FwpmIPsecTunnelAdd1
f1_keywords:
 - FwpmIPsecTunnelAdd1
 - fwpmk/FwpmIPsecTunnelAdd1
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmIPsecTunnelAdd1
---

## -description

The **FwpmIPsecTunnelAdd1** function adds a new Internet Protocol Security (IPsec) tunnel mode policy to the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param flags [in]

Possible values:

| IPsec tunnel flag | Meaning |
| --- | --- |
| **FWPM_TUNNEL_FLAG_POINT_TO_POINT** | Adds a point-to-point tunnel to the system. |
| **FWPM_TUNNEL_FLAG_ENABLE_VIRTUAL_IF_TUNNELING** | Enables virtual interface-based IPsec tunnel mode. |

### -param mainModePolicy [in, optional]

The Main Mode policy for the IPsec tunnel.

### -param tunnelPolicy [in]

The Quick Mode policy for the IPsec tunnel.

### -param numFilterConditions [in]

Number of filter conditions present in the *filterConditions* parameter.

### -param filterConditions [in]

Array of filter conditions that describe the traffic which should be tunneled by IPsec.

### -param keyModKey [in, optional]

Pointer to a GUID that uniquely identifies the keying module key.

If the caller supplies this parameter, only that keying module will be used for the tunnel. Otherwise, the default keying policy applies.

### -param sd [in, optional]

The security information associated with the IPsec tunnel.

## -returns

Type: <b>DWORD</b>

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The IPsec tunnel mode policy was successfully added. |
| **FWP_E_INVALID_PARAMETER**<br>0x80320035 | FWPM_TUNNEL_FLAG_POINT_TO_POINT was not set and conditions other than local/remote address were specified. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/desktop/FWP/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a read-only transaction, it fails with **FWP_E_INCOMPATIBLE_TXN**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

**FwpmIPsecTunnelAdd1** is a specific implementation of **FwpmIPsecTunnelAdd**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FWPM_FILTER_CONDITION0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_filter_condition0)**
- FWPM_PROVIDER_CONTEXT1
- [WFP Error Codes](/windows/desktop/FWP/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
