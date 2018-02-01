---
UID: NF:wdm.MmMapMdl
title: MmMapMdl function
author: windows-driver-content
description: This function maps physical pages described by a memory descriptor list (MDL) into the system virtual address space.
old-location: kernel\mmmapmdl.htm
old-project: kernel
ms.assetid: 4272f7a2-9379-40dd-a0a1-784dd25bc8bc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmMapMdl, wdm/MmMapMdl, kernel.mmmapmdl, MmMapMdl function [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmMapMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmMapMdl function


## -description


This function maps physical pages described by a memory descriptor
    list (MDL) into the system virtual address space.



## -syntax


````
 NTSTATUS  MmMapMdl(
  _In_ PMDL            MemoryDescriptorList,
  _In_ ULONG           Protection,
  _In_ PMM_MDL_ROUTINE DriverRoutine,
  _In_ PVOID           DriverContext
);
````


## -parameters




### -param MemoryDescriptorList [in]

A pointer to a valid MDL.


### -param Protection [in]

A bitwise of flags that indicates the protection to set for the pages. Possible values are PAGE_Xxx constants defined in Wdm.h.


### -param DriverRoutine [in]

 A pointer to a driver-supplied callback routine (<a href="..\wdm\nc-wdm-mm_mdl_routine.md">MM_MDL_ROUTINE</a>) that is invoked after the MDL is mapped.


### -param DriverContext [in]

A pointer to a driver-defined context. The driver's callback function can store any status information  in the driver context and then examine the value, when the callback is invoked. 


## -returns


    If the callback function pointed to by <i>DriverRoutine</i> was invoked, this function returns STATUS_SUCCESS. The function returns an appropriate NTSTATUS value if the MDL could not be mapped or the callback function could not be invoked.




## -see-also

<a href="..\wdm\nc-wdm-mm_mdl_routine.md">MM_MDL_ROUTINE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmMapMdl function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

