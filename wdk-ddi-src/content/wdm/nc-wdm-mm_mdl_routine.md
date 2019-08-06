---
UID: NC:wdm.MM_MDL_ROUTINE
title: MM_MDL_ROUTINE (wdm.h)
description: A driver-supplied callback routine that is invoked after a memory descriptor list (MDL) is mapped by calling the MmMapMdl function.
old-location: kernel\mm_mdl_routine.htm
tech.root: kernel
ms.assetid: D8D946C9-8642-4D31-B983-DAF88B46B97B
ms.date: 04/30/2018
ms.keywords: "*PMM_MDL_ROUTINE, *PMM_MDL_ROUTINE callback function [Kernel-Mode Driver Architecture], MM_MDL_ROUTINE, MM_MDL_ROUTINE callback, MmMdlRoutine, MmMdlRoutine callback function [Kernel-Mode Driver Architecture], kernel.mm_mdl_routine, wdm/MmMdlRoutine"
ms.topic: callback
f1_keywords:
 - "wdm/*PMM_MDL_ROUTINE"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- *PMM_MDL_ROUTINE
product:
- Windows
targetos: Windows
req.typenames: 
---

# MM_MDL_ROUTINE callback function


## -description


A driver-supplied callback routine that is invoked after a memory descriptor
    list (MDL)  is mapped by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmapmdl">MmMapMdl</a> function.


## -parameters




### -param DriverContext [in, optional]

A pointer to a driver-defined context. The driver's callback function can store any status information  in the driver context and then examine the value, when the callback is invoked. 


### -param MappedVa [in]

A pointer to a buffer that contains the system virtual address of the
        mapping.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmapmdl">MmMapMdl</a>
 

 

