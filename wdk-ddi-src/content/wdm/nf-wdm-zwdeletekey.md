---
UID: NF:wdm.ZwDeleteKey
title: ZwDeleteKey function (wdm.h)
description: The ZwDeleteKey routine deletes an open key from the registry.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwDeleteKey function"]
ms.keywords: NtDeleteKey, ZwDeleteKey, ZwDeleteKey routine [Kernel-Mode Driver Architecture], k111_b55bc28e-3539-424e-86b5-f7457e90cc61.xml, kernel.zwdeletekey, wdm/NtDeleteKey, wdm/ZwDeleteKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
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
 - ZwDeleteKey
 - wdm/ZwDeleteKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwDeleteKey
---

## -description

The **ZwDeleteKey** routine deletes an open key from the registry.

## -parameters

### -param KeyHandle [in]

Handle to the registry key to be deleted. The handle is created by a successful call to [ZwCreateKey](./nf-wdm-zwcreatekey.md) or [ZwOpenKey](./nf-wdm-zwopenkey.md).

## -returns

**ZwDeleteKey** returns an NTSTATUS value. Possible return values include:

- **STATUS_SUCCESS**

- **STATUS_ACCESS_DENIED**

- **STATUS_INVALID_HANDLE**

- **STATUS_CANNOT_DELETE** (see Remarks)

## -remarks

Before calling **ZwDeleteKey**, ensure that all the keys and values under the given key have been deleted. Delete each subkey first, starting with the leaf keys and work your way up.

The handle must have been opened for DELETE access for this routine to succeed. For more information, see the *DesiredAccess* parameter for [ZwCreateKey](./nf-wdm-zwcreatekey.md).

A call to **ZwDeleteKey** causes the handle that is specified in the *KeyHandle* parameter—and all other handles to the deleted key—to become invalid. After a call to **ZwDeleteKey** invalidates the key handles, you must call [ZwClose](../ntifs/nf-ntifs-ntclose.md) to close the key handles.

For more information about working with registry keys, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the call to this function occurs in user mode, you should use the name "**NtDeleteKey**" instead of "**ZwDeleteKey**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateKey](./nf-wdm-zwcreatekey.md)

[ZwOpenKey](./nf-wdm-zwopenkey.md)