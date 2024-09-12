---
UID: NF:fwpmk.FwpmIPsecTunnelDeleteByKey0
tech.root: netvista
title: FwpmIPsecTunnelDeleteByKey0
ms.date: 06/07/2024
targetos: Windows
description: The FwpmIPsecTunnelDeleteByKey0 function removes an Internet Protocol Security (IPsec) tunnel mode policy from the system.
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
 - FwpmIPsecTunnelDeleteByKey0
f1_keywords:
 - FwpmIPsecTunnelDeleteByKey0
 - fwpmk/FwpmIPsecTunnelDeleteByKey0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmIPsecTunnelDeleteByKey0
---

## -description

The **FwpmIPsecTunnelDeleteByKey0** function removes an Internet Protocol Security (IPsec) tunnel mode policy from the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param key [in]

Unique identifier of the IPsec tunnel. This GUID was specified in the providerContextKey member of the tunnelPolicy parameter of the **[FwpmIPsecTunnelAdd0](nf-fwpmk-fwpmipsectunneladd0.md)** function.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The IPsec tunnel mode policy was successfully deleted. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a read-only transaction, it fails with **FWP_E_INCOMPATIBLE_TXN**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

**FwpmIPsecTunnelDeleteByKey0** is a specific implementation of **FwpmIPsecTunnelDeleteByKey**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmIPsecTunnelAdd0](nf-fwpmk-fwpmipsectunneladd0.md)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
