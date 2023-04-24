---
UID: NF:wdm.ZwDeleteValueKey
title: ZwDeleteValueKey function (wdm.h)
description: The ZwDeleteValueKey routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwDeleteValueKey function"]
ms.keywords: NtDeleteValueKey, ZwDeleteValueKey, ZwDeleteValueKey routine [Kernel-Mode Driver Architecture], k111_81ff5c8c-442c-4ddd-9166-5445b964893a.xml, kernel.zwdeletevaluekey, wdm/NtDeleteValueKey, wdm/ZwDeleteValueKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwDeleteValueKey
 - wdm/ZwDeleteValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwDeleteValueKey
---

# ZwDeleteValueKey function

## -description

The **ZwDeleteValueKey** routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned.

## -parameters

### -param KeyHandle [in]

The handle to the registry key containing the value entry of interest. This key must have been opened with KEY_SET_VALUE set for the desired access. This handle is created by a successful call to [ZwCreateKey](./nf-wdm-zwcreatekey.md) or [ZwOpenKey](./nf-wdm-zwopenkey.md).

### -param ValueName [in]

Pointer to a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the name of the value entry to delete. This parameter can be an empty string if the value entry has no name.

## -returns

**ZwDeleteValueKey** returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following:

| Return code | Description |
|---|---|
| **STATUS_ACCESS_DENIED** | The *KeyHandle* handle does not have the KEY_SET_VALUE access. |
| **STATUS_INSUFFICIENT_RESOURCES** | Additional resources required by this function were not available. |
| **STATUS_INVALID_HANDLE** | The specified *KeyHandle* parameter was a **NULL** pointer or not a valid pointer to an open registry key. |
| **STATUS_OBJECT_NAME_NOT_FOUND** | The *ValueName* registry key entry was not found. |

## -remarks

The *KeyHandle* passed to **ZwDeleteValueKey** must have been opened for delete access to succeed. The *DesiredAccess* values of KEY_SET_VALUE, KEY_WRITE, and KEY_ALL_ACCESS include the KEY_SET_VALUE access mask required for delete access. For a description of possible values for *DesiredAccess*, see [ZwCreateKey](./nf-wdm-zwcreatekey.md).

If callback functions are registered for this registry key, then these callback functions will be called.

Device drivers should not attempt to call **ZwDeleteValueKey** directly to delete value entries in a subkey of the **\Registry..\ResourceMap** key. Only the system can write or delete value entries in the **\Registry..\HardwareDescription** tree.

If the call to this function occurs in user mode, you should use the name "**NtDeleteValueKey**" instead of "**ZwDeleteValueKey**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateKey](./nf-wdm-zwcreatekey.md)

[ZwDeleteKey](./nf-wdm-zwdeletekey.md)

[ZwEnumerateValueKey](./nf-wdm-zwenumeratevaluekey.md)

[ZwOpenKey](./nf-wdm-zwopenkey.md)

[ZwQueryValueKey](./nf-wdm-zwqueryvaluekey.md)

[ZwSetValueKey](./nf-wdm-zwsetvaluekey.md)