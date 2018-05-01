---
UID: NF:ntddk.IoAssignArcName
title: IoAssignArcName macro
author: windows-driver-content
description: The IoAssignArcName routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created.
old-location: kernel\ioassignarcname.htm
old-project: kernel
ms.assetid: ef8a132a-f593-4a25-bb9e-b4ed57801db2
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IoAssignArcName, IoAssignArcName routine [Kernel-Mode Driver Architecture], k104_ceeba02c-47cf-4c25-a339-d55ee9ebc216.xml, kernel.ioassignarcname, ntddk/IoAssignArcName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAssignArcName
product: Windows
targetos: Windows
req.typenames: 
---

# IoAssignArcName macro


## -description


The <b>IoAssignArcName</b> routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created.


## -parameters




### -param ArcName [in]

Pointer to a buffer containing the ARC name of the device. The ARC name must be a Unicode string.


### -param DeviceName [in]

Pointer to a buffer containing the name of the device object, representing the same device. The device object name must be a Unicode string. 


## -remarks



Drivers of hard disk devices need not call this routine. Drivers of other mass storage devices, including floppy, CD-ROM, and tape devices, should call <b>IoAssignArcName</b> during their initialization. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>
 

 

