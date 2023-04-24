---
UID: NF:wdm.ZwOpenSymbolicLinkObject
title: ZwOpenSymbolicLinkObject function (wdm.h)
description: The ZwOpenSymbolicLinkObject routine opens an existing symbolic link.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["ZwOpenSymbolicLinkObject function"]
ms.keywords: NtOpenSymbolicLinkObject, ZwOpenSymbolicLinkObject, ZwOpenSymbolicLinkObject routine [Kernel-Mode Driver Architecture], k111_8f2ddd22-26d2-438f-8335-fcc261735592.xml, kernel.zwopensymboliclinkobject, wdm/NtOpenSymbolicLinkObject, wdm/ZwOpenSymbolicLinkObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - ZwOpenSymbolicLinkObject
 - wdm/ZwOpenSymbolicLinkObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenSymbolicLinkObject
---

## -description

The **ZwOpenSymbolicLinkObject** routine opens an existing symbolic link.

## -parameters

### -param LinkHandle [out]

Pointer to a HANDLE variable that receives a handle to the symbolic link object.

### -param DesiredAccess [in]

Specifies an [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that determines the requested access to the object. The caller usually specified GENERIC_READ, so that the handle can be passed to [ZwQuerySymbolicLinkObject](./nf-wdm-zwquerysymboliclinkobject.md).

### -param ObjectAttributes [in]

Pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the object name and other attributes. Use [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls **InitializeObjectAttributes**.

## -returns

**ZwOpenSymbolicLinkObject** returns STATUS_SUCCESS on success or the appropriate error status.

## -remarks

Once the handle pointed to by *LinkHandle* is no longer in use, the driver must call [ZwClose](../ntifs/nf-ntifs-ntclose.md) to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see [Object Handles](/windows-hardware/drivers/kernel/object-handles).

If the call to the **ZwOpenSymbolicLinkObject** function occurs in user mode, you should use the name "NtOpenSymbolicLinkObject" instead of "**ZwOpenSymbolicLinkObject**".

**NtOpenSymbolicLinkObject** and **ZwOpenSymbolicLinkObject** are two versions of the same Windows Native System Services routine. The **NtOpenSymbolicLinkObject** routine in the Windows kernel is not directly accessible to kernel-mode drivers. However, kernel-mode drivers can access this routine indirectly by calling the **ZwOpenSymbolicLinkObject** routine.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwQuerySymbolicLinkObject](./nf-wdm-zwquerysymboliclinkobject.md)