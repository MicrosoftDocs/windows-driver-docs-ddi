---
UID: NF:wdm.CmCallbackGetKeyObjectID
title: CmCallbackGetKeyObjectID function (wdm.h)
description: The CmCallbackGetKeyObjectID routine retrieves the unique identifier and object name that are associated with a specified registry key object.
tech.root: kernel
ms.date: 12/09/2022
keywords: ["CmCallbackGetKeyObjectID function"]
ms.keywords: CmCallbackGetKeyObjectID, CmCallbackGetKeyObjectID routine [Kernel-Mode Driver Architecture], ConfigMgrRef_dbab8a69-78b4-4ae8-8409-e62e62ea8b9e.xml, kernel.cmcallbackgetkeyobjectid, wdm/CmCallbackGetKeyObjectID
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CmCallbackGetKeyObjectID
 - wdm/CmCallbackGetKeyObjectID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmCallbackGetKeyObjectID
---

## -description

The **CmCallbackGetKeyObjectID** routine retrieves the unique identifier and object name that are associated with a specified registry key object.

Starting with Windows 8, registry filter drivers should call the [CmCallbackGetKeyObjectIDEx](./nf-wdm-cmcallbackgetkeyobjectidex.md) routine instead of **CmCallbackGetKeyObjectID**. For more information, see the **Remarks** section below.

## -parameters

### -param Cookie [in]

The cookie value that the driver previously obtained by calling the [CmRegisterCallback](./nf-wdm-cmregistercallback.md) or [CmRegisterCallbackEx](./nf-wdm-cmregistercallbackex.md) routine.

### -param Object [in]

The pointer value that the driver's [RegistryCallback](./nc-wdm-ex_callback_function.md) callback routine received in the **Object** member of one of the **REG_*XXX*_KEY_INFORMATION** structures.

> [!WARNING]
> In certain circumstances registry callback notification structures may contain invalid non-NULL object pointers. Registry filtering drivers must not pass such pointers to this routine. For more information, see [Invalid Key Object Pointers in Registry Notifications](/windows-hardware/drivers/kernel/invalid-key-object-pointers-in-registry-notifications).

### -param ObjectID [out, optional]

A pointer to a location that receives a pointer to the unique identifier that represents the registry key that *Object* specifies. This parameter is optional and can be **NULL**.

### -param ObjectName [out, optional]

A pointer to a location that receives a pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure. This structure contains the object name of the registry key object that *Object* specifies. The object name is actually the full path name of the registry key that the object represents. The caller must not write to this **UNICODE_STRING** structure or free it. This parameter is optional and can be **NULL**.

## -returns

**CmCallbackGetKeyObjectID** returns STATUS_SUCCESS if the operation succeeds. Possible error return values include the following status code.

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The *Cookie* or *Object* parameter is invalid. |

## -remarks

The **CmCallbackGetKeyObjectID** routine is available starting with Windows Vista. An improved version of this routine, [CmCallbackGetKeyObjectIDEx](./nf-wdm-cmcallbackgetkeyobjectidex.md), is available starting with Windows 8. Drivers that run only in Windows 8 and later versions of Windows should call **CmCallbackGetKeyObjectIDEx** instead of **CmCallbackGetKeyObjectID**.

Drivers can use **CmCallbackGetKeyObjectID** to obtain the registry key identifier, the object name, or both, by supplying non-**NULL** values for the *ObjectID* or *ObjectName* parameters.

After the driver has obtained the identifier or name, the identifier or name is valid until the driver's *RegistryCallback* routine receives pre-notification of handle closure.

The driver must not modify the object name.

If two registry key objects represent the same registry key, the key identifiers for both objects are identical.

For more information about **CmCallbackGetKeyObjectID** and registry filtering operations, see [Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls).

## -see-also

[CmCallbackGetKeyObjectIDEx](./nf-wdm-cmcallbackgetkeyobjectidex.md)

[CmRegisterCallback](./nf-wdm-cmregistercallback.md)

[CmRegisterCallbackEx](./nf-wdm-cmregistercallbackex.md)

[RegistryCallback](./nc-wdm-ex_callback_function.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)