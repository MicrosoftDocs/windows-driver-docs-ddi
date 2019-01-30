---
UID: NF:wdm.MmMapMdl
title: MmMapMdl function (wdm.h)
description: This function maps physical pages described by a memory descriptor list (MDL) into the system virtual address space.
old-location: kernel\mmmapmdl.htm
tech.root: kernel
ms.assetid: 4272f7a2-9379-40dd-a0a1-784dd25bc8bc
ms.date: 04/30/2018
ms.keywords: MmMapMdl, MmMapMdl function [Kernel-Mode Driver Architecture], kernel.mmmapmdl, wdm/MmMapMdl
ms.topic: function
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmMapMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmMapMdl function


## -description


This function maps physical pages described by a memory descriptor
    list (MDL) into the system virtual address space.



## -parameters




### -param MemoryDescriptorList [in]

A pointer to a valid MDL.


### -param Protection [in]

A bitwise of flags that indicates the protection to set for the pages. Possible values are PAGE_Xxx constants defined in Wdm.h.


### -param DriverRoutine [in]

 A pointer to a driver-supplied callback routine (<a href="https://msdn.microsoft.com/D8D946C9-8642-4D31-B983-DAF88B46B97B">MM_MDL_ROUTINE</a>) that is invoked after the MDL is mapped.


### -param DriverContext [in]

A pointer to a driver-defined context. The driver's callback function can store any status information  in the driver context and then examine the value, when the callback is invoked. 


## -returns



    If the callback function pointed to by <i>DriverRoutine</i> was invoked, this function returns STATUS_SUCCESS. The function returns an appropriate NTSTATUS value if the MDL could not be mapped or the callback function could not be invoked.





## -see-also




<a href="https://msdn.microsoft.com/D8D946C9-8642-4D31-B983-DAF88B46B97B">MM_MDL_ROUTINE</a>
 

 

