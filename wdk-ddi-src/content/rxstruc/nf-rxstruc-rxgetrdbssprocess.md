---
UID: NF:rxstruc.RxGetRDBSSProcess
title: RxGetRDBSSProcess function
description: RxGetRDBSSProcess returns a pointer to the process of the main thread used by the RDBSS kernel process.
old-location: ifsk\rxgetrdbssprocess.htm
tech.root: ifsk
ms.assetid: 2d3717c2-c809-48b9-a84b-1e69a04b767e
ms.date: 04/16/2018
ms.keywords: RxGetRDBSSProcess, RxGetRDBSSProcess function [Installable File System Drivers], ifsk.rxgetrdbssprocess, rxref_7eee8a99-f7c3-41d3-8b16-1906ef301f47.xml, rxstruc/RxGetRDBSSProcess
ms.topic: function
req.header: rxstruc.h
req.include-header: Rxstruc.h, Ntddk.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxstruc.h
api_name:
-	RxGetRDBSSProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxGetRDBSSProcess function


## -description


<b>RxGetRDBSSProcess</b> returns a pointer to the process of the main thread used by the RDBSS kernel process.


## -parameters






## -returns



<b>RxGetRDBSSProcess</b> returns a pointer to the kernel process of the main thread used by RDBSS.




## -remarks



When <b>RxDriverEntry</b> is called to initialize RDBSS, a pointer to the kernel process that is running is retreived by calling <b>PsGetCurrentProcess</b> and stored in an internal RDBSS data structure. This value is returned when <b>RxGetRDBSSProcess</b> is called. This value is sometimes called the file system process. 




## -see-also




[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554404">RxDriverEntry</a>
 

 

