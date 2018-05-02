---
UID: NF:fltkernel.FltFreeGenericWorkItem
title: FltFreeGenericWorkItem function
author: windows-driver-content
description: The FltFreeGenericWorkItem routine frees a work item allocated by the FltAllocateGenericWorkItem routine.
old-location: ifsk\fltfreegenericworkitem.htm
old-project: ifsk
ms.assetid: 6675d529-10de-4c39-999c-4c18471ea6e0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_e8a6dadd-879e-4476-9433-40a065066445.xml, FltFreeGenericWorkItem, FltFreeGenericWorkItem routine [Installable File System Drivers], fltkernel/FltFreeGenericWorkItem, ifsk.fltfreegenericworkitem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltFreeGenericWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltFreeGenericWorkItem function


## -description


The <b>FltFreeGenericWorkItem</b> routine frees a work item allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541749">FltAllocateGenericWorkItem</a> routine. 


## -parameters




### -param FltWorkItem [in]

Opaque pointer to the work item to be freed. 


## -returns



None 




## -remarks



<b>FltFreeGenericWorkItem</b> frees an FLT_GENERIC_WORKITEM structure that was allocated by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541749">FltAllocateGenericWorkItem</a>. The freed memory is returned to nonpaged pool. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541749">FltAllocateGenericWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543452">FltQueueGenericWorkItem</a>
 

 

