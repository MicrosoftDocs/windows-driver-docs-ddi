---
UID: NF:wdm.ZwOpenKey
title: ZwOpenKey function (wdm.h)
description: The ZwOpenKey routine opens an existing registry key.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwOpenKey function"]
ms.keywords: ZwOpenKey, ZwOpenKey routine [Kernel-Mode Driver Architecture], k111_8583b145-a6be-4e4f-8e46-ca7d48b8a07f.xml, kernel.zwopenkey, wdm/ZwOpenKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate, ZwRegistryOpen(storport)
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
 - ZwOpenKey
 - wdm/ZwOpenKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenKey
---

## -description

The **ZwOpenKey** routine opens an existing registry key.

## -parameters

### -param KeyHandle [out]

Pointer to the HANDLE variable that receives the handle to the key.

### -param DesiredAccess [in]

Specifies an [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that determines the requested access to the object. For more information, see the *DesiredAccess* parameter of [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey).

### -param ObjectAttributes [in]

Pointer to an [OBJECT_ATTRIBUTES](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the object name and other attributes. Use [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls **InitializeObjectAttributes**.

## -returns

**ZwOpenKey** returns STATUS_SUCCESS if the given key was opened. Otherwise, it can return an error status, including the following:

- STATUS_INVALID_HANDLE

- STATUS_ACCESS_DENIED

## -remarks

**ZwOpenKey** supplies a handle that the caller can use to manipulate a registry key. The routine provides a subset of the functionality of [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey). For more information, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the specified key does not exist, **ZwOpenKey** returns an error status and does not return a key handle.

Once the handle pointed to by *KeyHandle* is no longer in use, the driver must call [ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose) to close it.

**ZwOpenKey** ignores the security information in the structure that the *ObjectAttributes* parameter points to.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see [Object Handles](/windows-hardware/drivers/kernel/object-handles).

For more information about working with registry keys, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the call to this function occurs in user mode, you should use the name "**NtOpenKey**" instead of "**ZwOpenKey**".

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)

[ZwDeleteKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwdeletekey)

[ZwEnumerateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratekey)

[ZwEnumerateValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey)

[ZwFlushKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwflushkey)

[ZwQueryKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwquerykey)

[ZwQueryValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey)

[ZwSetValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey)
