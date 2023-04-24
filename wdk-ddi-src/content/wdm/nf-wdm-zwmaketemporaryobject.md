---
UID: NF:wdm.ZwMakeTemporaryObject
title: ZwMakeTemporaryObject function (wdm.h)
description: The ZwMakeTemporaryObject routine changes the attributes of an object to make it temporary.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwMakeTemporaryObject function"]
ms.keywords: NtMakeTemporaryObject, ZwMakeTemporaryObject, ZwMakeTemporaryObject routine [Kernel-Mode Driver Architecture], k111_54a6768d-3f33-4c9e-8068-810401cad810.xml, kernel.zwmaketemporaryobject, wdm/NtMakeTemporaryObject, wdm/ZwMakeTemporaryObject
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
 - ZwMakeTemporaryObject
 - wdm/ZwMakeTemporaryObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwMakeTemporaryObject
---

## -description

The **ZwMakeTemporaryObject** routine changes the attributes of an object to make it temporary.

## -parameters

### -param Handle [in]

Handle to an object of any type.

## -returns

**ZwMakeTemporaryObject** returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.

## -remarks

**ZwMakeTemporaryObject** is a generic routine that operates on any type of object.

An object is permanent if it was created with the OBJ_PERMANENT object attribute specified. (For more information about object attributes, see [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes).) A permanent object is created with a reference count of 1, so it is not deleted when a driver dereferences it.

An object is temporary if it is not permanent. **ZwMakeTemporaryObject** turns the specified object into a temporary object. If the object is already temporary, this routine does nothing.

A temporary object has a name only as long as its handle count is greater than zero. When the handle count reaches zero, the system deletes the object name and appropriately adjusts the object's pointer count.

If the call to this function occurs in user mode, you should use the name "**NtMakeTemporaryObject**" instead of "**ZwMakeTemporaryObject**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwClose](../ntifs/nf-ntifs-ntclose.md)

[ZwCreateDirectoryObject](./nf-wdm-zwcreatedirectoryobject.md)

[ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md)