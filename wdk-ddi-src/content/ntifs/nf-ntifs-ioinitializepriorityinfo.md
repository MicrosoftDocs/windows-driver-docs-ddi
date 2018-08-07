---
UID: NF:ntifs.IoInitializePriorityInfo
title: IoInitializePriorityInfo function
author: windows-driver-content
description: The IoInitializePriorityInfo routine initializes a structure of type IO_PRIORITY_INFO.
old-location: ifsk\ioinitializepriorityinfo.htm
tech.root: ifsk
ms.assetid: 21aa5850-1984-4ab8-8e7c-3028fc87680b
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IoInitializePriorityInfo, IoInitializePriorityInfo routine [Installable File System Drivers], ifsk.ioinitializepriorityinfo, ioref_65eef333-11a8-4603-9b64-dc317f3d4e7b.xml, ntifs/IoInitializePriorityInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	IoInitializePriorityInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoInitializePriorityInfo function


## -description


The <b>IoInitializePriorityInfo</b> routine initializes a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>.


## -parameters




### -param PriorityInfo [in]

Pointer to a structure, of type IO_PRIORITY_INFO, to be initialized. This parameter is required and cannot be <b>NULL</b>.


## -returns



None. 




## -remarks



The <b>IoInitializePriorityInfo</b> routine is used to initialize the IO_PRIORITY_INFO structure that is utilized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548568">IO_PRIORITY_INFO</a>
 

 

