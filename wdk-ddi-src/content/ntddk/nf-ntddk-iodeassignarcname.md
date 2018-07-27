---
UID: NF:ntddk.IoDeassignArcName
title: IoDeassignArcName macro
author: windows-driver-content
description: The IoDeassignArcName routine removes a symbolic link between the ARC name for a device and the named device object.
old-location: kernel\iodeassignarcname.htm
tech.root: kernel
ms.assetid: 978fbe0a-ac10-4c83-870d-35d98775c233
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoDeassignArcName, IoDeassignArcName routine [Kernel-Mode Driver Architecture], k104_859767ed-5969-41db-a454-b7808a1ef131.xml, kernel.iodeassignarcname, ntddk/IoDeassignArcName
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
-	IoDeassignArcName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoDeassignArcName macro


## -description


The <b>IoDeassignArcName</b> routine removes a symbolic link between the ARC name for a device and the named device object. 


## -parameters




### -param ArcName [in]

Pointer to a buffered Unicode string that is the ARC name. 


## -remarks



<b>IoDeassignArcName</b> is generally called if the driver is deleting the device object, for example, when the driver is unloading. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548282">IoAssignArcName</a>
 

 

