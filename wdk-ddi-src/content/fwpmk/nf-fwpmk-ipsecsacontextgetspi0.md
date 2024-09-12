---
UID: NF:fwpmk.IPsecSaContextGetSpi0
tech.root: netvista
title: IPsecSaContextGetSpi0
ms.date: 06/20/2024
targetos: Windows
description: The IPsecSaContextGetSpi0 function retrieves the security parameters index (SPI) for a security association (SA) context.
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
 - IPsecSaContextGetSpi0
f1_keywords:
 - IPsecSaContextGetSpi0
 - fwpmk/IPsecSaContextGetSpi0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecSaContextGetSpi0
---

## -description

The **IPsecSaContextGetSpi0** function retrieves the security parameters index (SPI) for a security association (SA) context.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param id [in]

A runtime identifier for the SA context. This identifier was received from the system when the application called **[IPsecSaContextCreate0](nf-fwpmk-ipsecsacontextcreate0.md)**.

### -param getSpi [in]

The inbound IPsec traffic.

### -param inboundSpi [out]

The inbound SA SPI. The **IPSEC_SA_SPI** data type maps to the **UINT32** data type.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The SPI for the IPsec SA context was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller needs [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers) access to the IPsec security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IPsecSaContextGetSpi0** is a specific implementation of **IPsecSaContextGetSpi**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[IPsecSaContextCreate0](nf-fwpmk-ipsecsacontextcreate0.md)**
- [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers)
- [IPSEC_GETSPI0](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_getspi0)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
