---
UID: NF:fwpmk.FwpmConnectionSetSecurityInfo0
tech.root: netvista
title: FwpmConnectionSetSecurityInfo0
ms.date: 06/04/2024
targetos: Windows
description: The FwpmConnectionSetSecurityInfo0 function sets specified security information in the security descriptor for a connection object change event.
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
 - FwpmConnectionSetSecurityInfo0
f1_keywords:
 - FwpmConnectionSetSecurityInfo0
 - fwpmk/FwpmConnectionSetSecurityInfo0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmConnectionSetSecurityInfo0
---

## -description

The **FwpmConnectionSetSecurityInfo0** function sets specified security information in the security descriptor for a connection object change event.

## -parameters

### -param engineHandle [in]

A handle to an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param securityInfo [in]

The type of security information to set.

### -param sidOwner [in, optional]

The owner's security identifier (SID) to be set in the security descriptor.

### -param sidGroup [in, optional]

The group's SID to be set in the security descriptor.

### -param dacl [in, optional]

The discretionary access control list (DACL) to be set in the security descriptor.

### -param sacl [in, optional]

The system access control list (SACL) to be set in the security descriptor.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The security information was successfully set. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a transaction, it fails with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

This function cannot be called from within a dynamic session, it fails  with **FWP_E_DYNAMIC_SESSION_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about sessions.

This function behaves like the standard Win32 **[SetSecurityInfo](/windows/desktop/api/aclapi/nf-aclapi-setsecurityinfo)** function. The caller needs the same standard access rights as described in the **SetSecurityInfo** reference topic.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[SetSecurityInfo](/windows/desktop/api/aclapi/nf-aclapi-setsecurityinfo)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
