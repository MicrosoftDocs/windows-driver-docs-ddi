---
UID: NF:wdm.ZwMakeTemporaryObject
title: ZwMakeTemporaryObject function (wdm.h)
description: The ZwMakeTemporaryObject routine changes the attributes of an object to make it temporary.
old-location: kernel\zwmaketemporaryobject.htm
tech.root: kernel
ms.assetid: 1b58174f-aa38-4ea3-8e08-41434684e9ef
ms.date: 04/30/2018
keywords: ["ZwMakeTemporaryObject function"]
ms.keywords: NtMakeTemporaryObject, ZwMakeTemporaryObject, ZwMakeTemporaryObject routine [Kernel-Mode Driver Architecture], k111_54a6768d-3f33-4c9e-8068-810401cad810.xml, kernel.zwmaketemporaryobject, wdm/NtMakeTemporaryObject, wdm/ZwMakeTemporaryObject
f1_keywords:
 - "wdm/ZwMakeTemporaryObject"
 - "ZwMakeTemporaryObject"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwMakeTemporaryObject
- NtMakeTemporaryObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwMakeTemporaryObject function


## -description


The <b>ZwMakeTemporaryObject</b> routine changes the attributes of an object to make it temporary.


## -parameters




### -param Handle [in]

Handle to an object of any type. 


## -returns



<b>ZwMakeTemporaryObject</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



<b>ZwMakeTemporaryObject</b> is a generic routine that operates on any type of object.

An object is permanent if it was created with the OBJ_PERMANENT object attribute specified. (For more information about object attributes, see <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>.) A permanent object is created with a reference count of 1, so it is not deleted when a driver dereferences it. 

An object is temporary if it is not permanent. <b>ZwMakeTemporaryObject</b> turns the specified object into a temporary object. If the object is already temporary, this routine does nothing.

A temporary object has a name only as long as its handle count is greater than zero. When the handle count reaches zero, the system deletes the object name and appropriately adjusts the object's pointer count.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtMakeTemporaryObject</b>" instead of "<b>ZwMakeTemporaryObject</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatedirectoryobject">ZwCreateDirectoryObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>
 

 

