---
UID: NF:fwpmk.FwpmCalloutGetSecurityInfoByKey0
tech.root: netvista
title: FwpmCalloutGetSecurityInfoByKey0
ms.date: 06/04/2024
targetos: Windows
description: The FwpmCalloutGetSecurityInfoByKey0 function retrieves a copy of the security descriptor for a callout object.
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
 - FwpmCalloutGetSecurityInfoByKey0
f1_keywords:
 - FwpmCalloutGetSecurityInfoByKey0
 - fwpmk/FwpmCalloutGetSecurityInfoByKey0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmCalloutGetSecurityInfoByKey0
---

## -description

The **FwpmCalloutGetSecurityInfoByKey0** function retrieves a copy of the security descriptor for a callout object.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param key [in, optional]

Pointer to a GUID that uniquely identifies the callout. This GUID was specified in the **calloutKey** member of the *callout* parameter when the application called **[FwpmCalloutAdd0](nf-fwpmk-fwpmcalloutadd0.md)** for this object.

### -param securityInfo [in]

The type of security information to retrieve.

### -param sidOwner [out]

The owner security identifier (SID) in the returned security descriptor.

### -param sidGroup [out]

The primary group security identifier (SID) in the returned security descriptor.

### -param dacl [out]

The discretionary access control list (DACL) in the returned security descriptor.

### -param sacl [out]

The system access control list (SACL) in the returned security descriptor.

### -param securityDescriptor [out]

The returned security descriptor.

## -returns

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The security descriptor was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If the key parameter is **NULL** or if it is a **NULL** GUID, this function manages the security information of the callouts container.

The returned *securityDescriptor* parameter must be freed through a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**. The other four (optional) returned parameters must not be freed, as they point to addresses within the *securityDescriptor* parameter.

This function behaves like the standard Win32 **[GetSecurityInfo](/windows/win32/api/aclapi/nf-aclapi-getsecurityinfo)** function. The caller needs the same standard access rights as described in the **GetSecurityInfo** reference topic.

**FwpmCalloutGetSecurityInfoByKey0** is a specific implementation of **FwpmCalloutGetSecurityInfoByKey**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/win32/fwp/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmCalloutAdd0](nf-fwpmk-fwpmcalloutadd0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- **[GetSecurityInfo](/windows/win32/api/aclapi/nf-aclapi-getsecurityinfo)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/win32/fwp/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
