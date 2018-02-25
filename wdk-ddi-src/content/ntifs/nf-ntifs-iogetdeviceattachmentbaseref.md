---
UID: NF:ntifs.IoGetDeviceAttachmentBaseRef
title: IoGetDeviceAttachmentBaseRef function
author: windows-driver-content
description: The IoGetDeviceAttachmentBaseRef routine returns a pointer to the lowest-level device object in a file system or device driver stack.
old-location: ifsk\iogetdeviceattachmentbaseref.htm
old-project: ifsk
ms.assetid: e1d31fdd-de4f-4e57-a8e8-0468ab4242f8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, B, D, G, I, IoGetDeviceAttachmentBaseRef, IoGetDeviceAttachmentBaseRef routine [Installable File System Drivers], R, a, c, e, f, h, i, ifsk.iogetdeviceattachmentbaseref, ioref_ab9c898e-74be-48aa-9462-d78d0e34c435.xml, m, n, ntifs/IoGetDeviceAttachmentBaseRef, o, s, t, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetDeviceAttachmentBaseRef
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetDeviceAttachmentBaseRef function


## -description


The <b>IoGetDeviceAttachmentBaseRef</b> routine returns a pointer to the lowest-level device object in a file system or device driver stack.


## -syntax


````
PDEVICE_OBJECT IoGetDeviceAttachmentBaseRef(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

A pointer to a device object in the stack.


## -returns



<b>IoGetDeviceAttachmentBaseRef</b> returns a pointer to the device object at the bottom of the file system or device driver stack. If the given device object is not attached to a driver stack, <b>IoGetDeviceAttachmentBaseRef</b> returns  the device object pointer in <i>DeviceObject</i>. 




## -remarks



A file system filter driver typically calls <b>IoGetDeviceAttachmentBaseRef</b> to get the lowest-level device object in a file system driver stack. Often this is done when the filter driver receives notification that a file system has registered or unregistered itself as an active file system. The filter driver's notification callback routine calls <b>IoGetDeviceAttachmentBaseRef</b> to get a pointer to the file system's control device object, and then calls <a href="..\ntifs\nf-ntifs-obquerynamestring.md">ObQueryNameString</a> to retrieve this object's name for debugging purposes. 

<b>IoGetDeviceAttachmentBaseRef</b> increments the reference count on the device object at the bottom of the stack. Thus every successful call to <b>IoGetDeviceAttachmentBaseRef</b> must be matched by a subsequent call to <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>



<a href="..\ntifs\nf-ntifs-iogetlowerdeviceobject.md">IoGetLowerDeviceObject</a>



<a href="..\ntifs\nf-ntifs-ioenumeratedeviceobjectlist.md">IoEnumerateDeviceObjectList</a>



<a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\ntifs\nf-ntifs-obquerynamestring.md">ObQueryNameString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetDeviceAttachmentBaseRef routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

