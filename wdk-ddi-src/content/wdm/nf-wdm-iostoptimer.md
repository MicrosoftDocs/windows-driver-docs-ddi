---
UID: NF:wdm.IoStopTimer
title: IoStopTimer function
author: windows-driver-content
description: The IoStopTimer routine disables the timer for a specified device object so the driver-supplied IoTimer routine is not called.
old-location: kernel\iostoptimer.htm
tech.root: kernel
ms.assetid: 4b903046-8f96-4299-94e7-85900be1bbd4
ms.date: 4/30/2018
ms.keywords: IoStopTimer, IoStopTimer routine [Kernel-Mode Driver Architecture], k104_dfedf779-1137-44c1-ab06-223c3ce6e9c6.xml, kernel.iostoptimer, wdm/IoStopTimer
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoStopTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoStopTimer function


## -description


The <b>IoStopTimer</b> routine disables the timer for a specified device object so the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a> routine is not called. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object with which the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a> routine is associated.


## -returns



None




## -remarks



The driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a> routine can be reenabled with a call to <b>IoStartTimer</b>.

Do not call <b>IoStopTimer</b> from within the <i>IoTimer</i> routine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549344">IoInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550373">IoStartTimer</a>
 

 

