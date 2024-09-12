---
UID: NF:fwpmk.IPsecSaCreateEnumHandle0
tech.root: netvista
title: IPsecSaCreateEnumHandle0
ms.date: 06/20/2024
targetos: Windows
description: The IPsecSaCreateEnumHandle0 function creates a handle used to enumerate a set of Internet Protocol Security (IPsec) security association (SA) objects.
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
 - IPsecSaCreateEnumHandle0
f1_keywords:
 - IPsecSaCreateEnumHandle0
 - fwpmk/IPsecSaCreateEnumHandle0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecSaCreateEnumHandle0
---

## -description

The **IPsecSaCreateEnumHandle0** function creates a handle used to enumerate a set of Internet Protocol Security (IPsec) security association (SA) objects.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumTemplate [in, optional]

Template to selectively restrict the enumeration.

### -param enumHandle [out]

Handle of the newly created enumeration.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The enumeration was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller must call **[IPsecSaDestroyEnumHandle0](nf-fwpmk-ipsecsadestroyenumhandle0.md)** to free the returned handle.

The caller needs [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers) and [FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers) access to the IPsec security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IPsecSaCreateEnumHandle0** is a specific implementation of **IPsecSaCreateEnumHandle**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[IPsecSaDestroyEnumHandle0](nf-fwpmk-ipsecsadestroyenumhandle0.md)**
- [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers)
- [FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)
- [IPSEC_SA_ENUM_TEMPLATE0](/windows/desktop/api/ipsectypes/ns-ipsectypes-ipsec_sa_enum_template0)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
