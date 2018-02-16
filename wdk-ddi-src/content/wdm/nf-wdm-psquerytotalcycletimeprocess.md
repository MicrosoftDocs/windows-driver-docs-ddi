---
UID: NF:wdm.PsQueryTotalCycleTimeProcess
title: PsQueryTotalCycleTimeProcess function
author: windows-driver-content
description: The PsQueryTotalCycleTimeProcess routine returns the accumulated cycle time for the specified process.
old-location: kernel\psquerytotalcycletimeprocess.htm
old-project: kernel
ms.assetid: 4DA34F96-A69A-46BE-B3D8-D542794052DE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PsQueryTotalCycleTimeProcess, PsQueryTotalCycleTimeProcess routine [Kernel-Mode Driver Architecture], kernel.psquerytotalcycletimeprocess, PsQueryTotalCycleTimeProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ntoskrnl.lib
-	ntoskrnl.dll
apiname:
-	PsQueryTotalCycleTimeProcess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PsQueryTotalCycleTimeProcess function


## -description


The <b>PsQueryTotalCycleTimeProcess</b> routine returns the accumulated cycle time for the specified process.


## -syntax


````
ULONG64 PsQueryTotalCycleTimeProcess(
  _Inout_ PEPROCESS Process,
  _Out_   PULONG64  CycleTimeStamp
);
````


## -parameters




### -param Process [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544273">EPROCESS</a> structure that serves as the kernel object for the process.


### -param CycleTimeStamp [out]

A pointer to a ULONG64 variable to which the routine writes the current cycle counter value for the process.


## -returns



<b>PsQueryTotalCycleTimeProcess</b> returns the accumulated cycle time for the specified process.




## -remarks



This routine uses the time stamp counter to get the number of processor clock cycles used by the specified process.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544273">EPROCESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsQueryTotalCycleTimeProcess routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

