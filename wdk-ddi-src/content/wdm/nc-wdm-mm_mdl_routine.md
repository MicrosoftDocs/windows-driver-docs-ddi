---
UID: NC:wdm.MM_MDL_ROUTINE
title: MM_MDL_ROUTINE
author: windows-driver-content
description: A driver-supplied callback routine that is invoked after a memory descriptor list (MDL) is mapped by calling the MmMapMdl function.
old-location: kernel\mm_mdl_routine.htm
old-project: kernel
ms.assetid: D8D946C9-8642-4D31-B983-DAF88B46B97B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.mm_mdl_routine, MmMdlRoutine callback function [Kernel-Mode Driver Architecture], MmMdlRoutine, MM_MDL_ROUTINE, MM_MDL_ROUTINE, wdm/MmMdlRoutine, *PMM_MDL_ROUTINE callback function [Kernel-Mode Driver Architecture], *PMM_MDL_ROUTINE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	*PMM_MDL_ROUTINE
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# MM_MDL_ROUTINE callback


## -description


A driver-supplied callback routine that is invoked after a memory descriptor
    list (MDL)  is mapped by calling the <a href="..\wdm\nf-wdm-mmmapmdl.md">MmMapMdl</a> function.


## -prototype


````
MM_MDL_ROUTINE MmMdlRoutine;

VOID MmMdlRoutine(
  _In_opt_ PVOID DriverContext,
  _In_     PVOID MappedVa
)
{ ... }

typedef MM_MDL_ROUTINE *PMM_MDL_ROUTINE;
````


## -parameters




#### - DriverContext [in, optional]

A pointer to a driver-defined context. The driver's callback function can store any status information  in the driver context and then examine the value, when the callback is invoked. 


#### - MappedVa [in]

A pointer to a buffer that contains the system virtual address of the
        mapping.


## -returns


This callback function does not return a value.



## -see-also

<a href="..\wdm\nf-wdm-mmmapmdl.md">MmMapMdl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MM_MDL_ROUTINE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

