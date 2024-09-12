---
UID: NF:fwpmk.IkeextGetStatistics0
tech.root: netvista
title: IkeextGetStatistics0
ms.date: 06/19/2024
targetos: Windows
description: The IkeextGetStatistics0 function retrieves Internet Key Exchange (IKE) and Authenticated Internet Protocol (AuthIP) statistics.
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
 - IkeextGetStatistics0
f1_keywords:
 - IkeextGetStatistics0
 - fwpmk/IkeextGetStatistics0
dev_langs:
 - c++
helpviewer_keywords:
 - IkeextGetStatistics0
---

## -description

The **IkeextGetStatistics0** function retrieves Internet Key Exchange (IKE) and Authenticated Internet Protocol (AuthIP) statistics.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param ikeextStatistics [out]

The top-level object of IKE/AuthIP statistics organization.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The information was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller needs [FWPM_ACTRL_READ_STATS](/windows/desktop/FWP/access-right-identifiers) access to the IKE/AuthIP security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IkeextGetStatistics0** is a specific implementation of **IkeextGetStatistics**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [FWPM_ACTRL_READ_STATS](/windows/desktop/FWP/access-right-identifiers)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
- [IKE/AuthIP Functions](/windows/desktop/FWP/fwp-ike-functions)
- [WFP Functions](/windows/desktop/FWP/fwp-functions)
- [Windows Filtering Platform API Reference](/windows/desktop/FWP/fwp-reference)
