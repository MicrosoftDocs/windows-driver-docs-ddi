---
UID: NF:fwpmk.IPsecSaContextDeleteById0
tech.root: netvista
title: IPsecSaContextDeleteById0
ms.date: 06/20/2024
targetos: Windows
description: The IPsecSaContextDeleteById0 function deletes an IPsec security association (SA) context.
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
 - IPsecSaContextDeleteById0
f1_keywords:
 - IPsecSaContextDeleteById0
 - fwpmk/IPsecSaContextDeleteById0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecSaContextDeleteById0
---

## -description

The **IPsecSaContextDeleteById0** function deletes an IPsec security association (SA) context.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param id [in]

A runtime identifier for the object being removed from the system. This identifier was received from the system when the application called **[IPsecSaContextCreate0](nf-fwpmk-ipsecsacontextcreate0.md)**.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The IPsec SA context was successfully deleted. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a transaction, it fails with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

This function cannot be called from within a dynamic session. The call fails with **FWP_E_DYNAMIC_SESSION_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about dynamic sessions.

The caller needs [DELETE](/windows/desktop/SecAuthZ/standard-access-rights) access to the IPsec security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**IPsecSaContextDeleteById0** is a specific implementation of **IPsecSaContextDeleteById**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

Here are all the markdown links in the current document:

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[IPsecSaContextCreate0](nf-fwpmk-ipsecsacontextcreate0.md)**
- [DELETE](/windows/desktop/SecAuthZ/standard-access-rights)
- [Access Control](/windows/desktop/FWP/access-control)
- [Object Management](/windows/desktop/FWP/object-management)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
