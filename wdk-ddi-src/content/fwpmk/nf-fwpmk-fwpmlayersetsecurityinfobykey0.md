---
UID: NF:fwpmk.FwpmLayerSetSecurityInfoByKey0
tech.root: netvista
title: FwpmLayerSetSecurityInfoByKey0
ms.date: 05/30/2024
targetos: Windows
description: The FwpmLayerSetSecurityInfoByKey0 function sets specified security information in the security descriptor of a layer object.
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
 - FwpmLayerSetSecurityInfoByKey0
f1_keywords:
 - FwpmLayerSetSecurityInfoByKey0
 - fwpmk/FwpmLayerSetSecurityInfoByKey0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmLayerSetSecurityInfoByKey0
---

## -description

The **FwpmLayerSetSecurityInfoByKey0** function sets specified security information in the security descriptor of a layer object.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param key

Unique identifier of the layer. See [Filtering Layer Identifiers](/windows/desktop/FWP/management-filtering-layer-identifiers-) for a list of possible GUID values.

### -param securityInfo

The type of security information to set.

### -param sidOwner

The owner's security identifier (SID) to be set in the security descriptor.

### -param sidGroup

The group's SID to be set in the security descriptor.

### -param dacl

The discretionary access control list (DACL) to be set in the security descriptor.

### -param sacl

The system access control list (SACL) to be set in the security descriptor.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The security descriptor was set successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the *key* parameter is **NULL** or if it is a **NULL** GUID, this function manages the security information of the layers container.

This function cannot be called from within a transaction, it fails with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

This function behaves like the standard Win32 **[SetSecurityInfo](/windows/desktop/api/aclapi/nf-aclapi-setsecurityinfo)** function. The caller needs the same standard access rights as described in the **SetSecurityInfo** reference topic.

**FwpmLayerSetSecurityInfoByKey0** is a specific implementation of **FwpmLayerSetSecurityInfoByKey**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmLayerGetSecurityInfoByKey0](nf-fwpmk-fwpmlayergetsecurityinfobykey0.md)**
- **[SetSecurityInfo](/windows/desktop/api/aclapi/nf-aclapi-setsecurityinfo)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
- [Object Management](/windows/desktop/FWP/object-management)
