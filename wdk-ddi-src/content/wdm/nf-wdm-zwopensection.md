---
UID: NF:wdm.ZwOpenSection
title: ZwOpenSection function (wdm.h)
description: The ZwOpenSection routine opens a handle for an existing section object.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwOpenSection function"]
ms.keywords: NtOpenSection, ZwOpenSection, ZwOpenSection routine [Kernel-Mode Driver Architecture], k111_51851f81-8825-499b-9e7e-36faa8f53b23.xml, kernel.zwopensection, wdm/NtOpenSection, wdm/ZwOpenSection
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
 - ZwOpenSection
 - wdm/ZwOpenSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenSection
---

## -description

The **ZwOpenSection** routine opens a handle for an existing [section object](/windows-hardware/drivers/).

## -parameters

### -param SectionHandle [out]

Pointer to a HANDLE variable that receives a handle to the section object.

### -param DesiredAccess [in]

Specifies an [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that determines the requested access to the object. For more information, see the *DesiredAccess* parameter of [ZwCreateSection](./nf-wdm-zwcreatesection.md).

### -param ObjectAttributes [in]

Pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the object name and other attributes. Use [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls **InitializeObjectAttributes**.

## -returns

**ZwOpenSection** returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible return values include:

## -remarks

If the section does not exist or the system did not grant the requested access, the operation fails.

Once the handle pointed to by *SectionHandle* is no longer in use, the driver must call [ZwClose](../ntifs/nf-ntifs-ntclose.md) to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see [Object Handles](/windows-hardware/drivers/kernel/object-handles).

If the call to this function occurs in user mode, you should use the name "**NtOpenSection**" instead of "**ZwOpenSection**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateSection](./nf-wdm-zwcreatesection.md)

[ZwMapViewOfSection](./nf-wdm-zwmapviewofsection.md)

[ZwUnmapViewOfSection](./nf-wdm-zwunmapviewofsection.md)