---
UID: NF:fltkernel.FltFreeGenericWorkItem
title: FltFreeGenericWorkItem function
author: windows-driver-content
description: The FltFreeGenericWorkItem routine frees a work item allocated by the FltAllocateGenericWorkItem routine.
old-location: ifsk\fltfreegenericworkitem.htm
old-project: ifsk
ms.assetid: 6675d529-10de-4c39-999c-4c18471ea6e0
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFreeGenericWorkItem routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

