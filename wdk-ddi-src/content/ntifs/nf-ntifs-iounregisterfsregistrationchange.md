---
UID: NF:ntifs.IoUnregisterFsRegistrationChange
title: IoUnregisterFsRegistrationChange function
author: windows-driver-content
description: The IoUnregisterFsRegistrationChange routine unregisters file system filter driver's file system registration change notification routine.
old-location: ifsk\iounregisterfsregistrationchange.htm
old-project: ifsk
ms.assetid: 4e10afc0-b9c4-4495-83a1-11f9b82143fc
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: IoUnregisterFsRegistrationChange, ioref_18a53f5a-49f9-40ba-bf85-d2fea7d6fbfb.xml, IoUnregisterFsRegistrationChange routine [Installable File System Drivers], ifsk.iounregisterfsregistrationchange, ntifs/IoUnregisterFsRegistrationChange
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
-	IoUnregisterFsRegistrationChange
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoUnregisterFsRegistrationChange function


## -description


The <b>IoUnregisterFsRegistrationChange</b> routine unregisters file system filter driver's file system registration change notification routine.


## -syntax


````
VOID IoUnregisterFsRegistrationChange(
  _In_ PDRIVER_OBJECT          DriverObject,
  _In_ PDRIVER_FS_NOTIFICATION DriverNotificationRoutine
);
````


## -parameters




### -param DriverObject [in]

Pointer to the driver object for the filter driver.


### -param DriverNotificationRoutine [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551037">PDRIVER_FS_NOTIFICATION</a> routine, which the file system calls when it registers or unregisters itself.


## -returns



None




## -remarks



<b>IoUnregisterFsRegistrationChange</b> unregisters a file system filter driver's notification routine so that it is no longer called whenever a file system calls <a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a> or <a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>. <b>IoUnregisterFsRegistrationChange</b> also decrements the reference count on the filter driver's driver object.




## -see-also

<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>



<a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a>



<a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoUnregisterFsRegistrationChange routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

