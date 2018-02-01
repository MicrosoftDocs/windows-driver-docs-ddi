---
UID: NF:ntifs.IoRegisterFileSystem
title: IoRegisterFileSystem function
author: windows-driver-content
description: The IoRegisterFileSystem routine adds a file system's control device object to the global file system queue.
old-location: ifsk\ioregisterfilesystem.htm
old-project: ifsk
ms.assetid: 19d53afd-b63c-4fd3-9b08-c51e2a1247af
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/IoRegisterFileSystem, IoRegisterFileSystem routine [Installable File System Drivers], ifsk.ioregisterfilesystem, ioref_42200300-9ef6-4be9-8fee-bf42b027a809.xml, IoRegisterFileSystem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoRegisterFileSystem
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoRegisterFileSystem function


## -description


The <b>IoRegisterFileSystem</b> routine adds a file system's control device object to the global file system queue.


## -syntax


````
VOID IoRegisterFileSystem(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the control device object for the file system.


## -returns


None



## -remarks


<b>IoRegisterFileSystem</b> registers a file system as an active file system by inserting the file system's control device object into the global file system queue, and increments the reference count on the file system's control device object.

The file system control device object's device type must be one of the following:

FILE_DEVICE_NETWORK_FILE_SYSTEM

FILE_DEVICE_CD_ROM_FILE_SYSTEM

FILE_DEVICE_DISK_FILE_SYSTEM

If the device type is not one of these values, the file system is not registered.

In addition, the file system control device object must be named. If it is not named, this does not cause the call to <b>IoRegisterFileSystem</b> to fail. However, file system filter drivers, as well as many system components and support routines, use this name to distinguish the file system's control device objects, which are always named, from its volume device objects, which are never named. 

If the DO_LOW_PRIORITY_FILESYSTEM flag is set on the file system's control device object, the device object is inserted into the next-to-last position in the queue. (The RAW file system occupies the last position in the queue.) If this flag is not set, the device object is inserted at the head of the queue.

<b>IoRegisterFileSystem</b> calls the notification routines of file system filter drivers that have registered for this notification by calling <a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a> or <a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchangeex.md">IoRegisterFsRegistrationChangeEx</a>.
<div class="alert"><b>Note</b>    In Microsoft Windows XP and later, when a file system filter driver calls <a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>, its notification routine is also called immediately for any file systems that have already called <b>IoRegisterFileSystem</b>. </div><div> </div>


## -see-also

<a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>

<a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>

<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchangeex.md">IoRegisterFsRegistrationChangeEx</a>

<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoRegisterFileSystem routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

