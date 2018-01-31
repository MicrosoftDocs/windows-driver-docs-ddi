---
UID: NF:wdm.ZwMakeTemporaryObject
title: ZwMakeTemporaryObject function
author: windows-driver-content
description: The ZwMakeTemporaryObject routine changes the attributes of an object to make it temporary.
old-location: kernel\zwmaketemporaryobject.htm
old-project: kernel
ms.assetid: 1b58174f-aa38-4ea3-8e08-41434684e9ef
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k111_54a6768d-3f33-4c9e-8068-810401cad810.xml, ZwMakeTemporaryObject, kernel.zwmaketemporaryobject, NtMakeTemporaryObject, wdm/ZwMakeTemporaryObject, ZwMakeTemporaryObject routine [Kernel-Mode Driver Architecture], wdm/NtMakeTemporaryObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwMakeTemporaryObject
-	NtMakeTemporaryObject
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwMakeTemporaryObject function


## -description


The <b>ZwMakeTemporaryObject</b> routine changes the attributes of an object to make it temporary.


## -syntax


````
NTSTATUS ZwMakeTemporaryObject(
  _In_ HANDLE Handle
);
````


## -parameters




#### - Handle [in]

Handle to an object of any type. 


## -returns


<b>ZwMakeTemporaryObject</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.



## -remarks


<b>ZwMakeTemporaryObject</b> is a generic routine that operates on any type of object.

An object is permanent if it was created with the OBJ_PERMANENT object attribute specified. (For more information about object attributes, see <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>.) A permanent object is created with a reference count of 1, so it is not deleted when a driver dereferences it. 

An object is temporary if it is not permanent. <b>ZwMakeTemporaryObject</b> turns the specified object into a temporary object. If the object is already temporary, this routine does nothing.

A temporary object has a name only as long as its handle count is greater than zero. When the handle count reaches zero, the system deletes the object name and appropriately adjusts the object's pointer count.
<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtMakeTemporaryObject</b>" instead of "<b>ZwMakeTemporaryObject</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.



## -see-also

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\wdm\nf-wdm-zwcreatedirectoryobject.md">ZwCreateDirectoryObject</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwMakeTemporaryObject routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

