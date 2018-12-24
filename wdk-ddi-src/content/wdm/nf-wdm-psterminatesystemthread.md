---
UID: NF:wdm.PsTerminateSystemThread
title: PsTerminateSystemThread function
description: The PsTerminateSystemThread routine terminates the current system thread.
old-location: kernel\psterminatesystemthread.htm
tech.root: kernel
ms.assetid: 04f9f699-0ca1-4b22-b66f-04fcf53935c4
ms.date: 04/30/2018
ms.keywords: PsTerminateSystemThread, PsTerminateSystemThread routine [Kernel-Mode Driver Architecture], k108_a8e19a60-578c-42a6-b77a-cf6c4098c815.xml, kernel.psterminatesystemthread, wdm/PsTerminateSystemThread
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlPsPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsTerminateSystemThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsTerminateSystemThread function


## -description


The <b>PsTerminateSystemThread</b> routine terminates the current system thread.


## -parameters




### -param ExitStatus [in]

Specifies the status of the terminating system thread. 


## -returns



<b>PsTerminateSystemThread</b> does not return if it successfully terminates the calling thread. If the routine cannot terminate the thread (for example, if the thread is not a system thread), the routine returns an error NTSTATUS value. 




## -remarks



A system thread calls <b>PsTerminateSystemThread</b> to terminate itself. A driver that creates its own threads must ensure that each such thread terminates. The driver must not terminate any threads that the system or other drivers created. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559932">PsCreateSystemThread</a>
 

 

