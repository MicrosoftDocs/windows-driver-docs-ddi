---
UID: NF:fwpmk.IPsecGetStatistics0
tech.root: netvista
title: IPsecGetStatistics0
ms.date: 06/20/2024
targetos: Windows
description: The IPsecGetStatistics0 function retrieves Internet Protocol Security (IPsec) statistics.
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
 - IPsecGetStatistics0
f1_keywords:
 - IPsecGetStatistics0
 - fwpmk/IPsecGetStatistics0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecGetStatistics0
---

## -description

The **IPsecGetStatistics0** function retrieves Internet Protocol Security (IPsec) statistics.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param ipsecStatistics [out]

Top-level object of IPsec statistics organization.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The IPsec statistics were successfully retrieved. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a transaction, it fails with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

The caller needs [FWPM_ACTRL_READ_STATS](/windows/desktop/FWP/access-right-identifiers) access to the IPsec security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IPsecGetStatistics0** is a specific implementation of **IPsecGetStatistics**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [IPSEC_STATISTICS0](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_statistics0)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [FWPM_ACTRL_READ_STATS](/windows/desktop/FWP/access-right-identifiers)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
