---
UID: NF:fwpmk.IPsecDospStateCreateEnumHandle0
tech.root: netvista
title: IPsecDospStateCreateEnumHandle0
ms.date: 06/20/2024
targetos: Windows
description: The IPsecDospStateCreateEnumHandle0 function creates a handle used to enumerate a set of IPsec DoS Protection objects.
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
 - IPsecDospStateCreateEnumHandle0
f1_keywords:
 - IPsecDospStateCreateEnumHandle0
 - fwpmk/IPsecDospStateCreateEnumHandle0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecDospStateCreateEnumHandle0
---

## -description

The **IPsecDospStateCreateEnumHandle0** function creates a handle used to enumerate a set of IPsec DoS Protection objects.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumTemplate [in, optional]

Template for selectively restricting the enumeration.

### -param enumHandle [out]

Address of a **HANDLE** variable. On function return, it contains the handle for the newly created enumeration.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The enumeration was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If *enumTemplate* is **NULL**, all IPsec DoS Protection objects are returned.

The caller must call **[IPsecDospStateDestroyEnumHandle0](nf-fwpmk-ipsecdospstatedestroyenumhandle0.md)** to free the returned handle.

The caller needs [FWPM_ACTRL_READ_STATS](/windows/desktop/FWP/access-right-identifiers) access to the IPsec DoS Protection component. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IPsecDospStateCreateEnumHandle0** is a specific implementation of **IPsecDospStateCreateEnumHandle**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[IPsecDospStateDestroyEnumHandle0](nf-fwpmk-ipsecdospstatedestroyenumhandle0.md)**
- [IPSEC_DOSP_STATE_ENUM_TEMPLATE0](/windows/win32/api/ipsectypes/ns-ipsectypes-ipsec_dosp_state_enum_template0)
- [FWPM_ACTRL_READ_STATS](/windows/desktop/FWP/access-right-identifiers)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
