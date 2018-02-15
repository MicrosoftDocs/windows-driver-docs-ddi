---
UID: NF:wdm.PsTerminateSystemThread
title: PsTerminateSystemThread function
author: windows-driver-content
description: The PsTerminateSystemThread routine terminates the current system thread.
old-location: kernel\psterminatesystemthread.htm
old-project: kernel
ms.assetid: 04f9f699-0ca1-4b22-b66f-04fcf53935c4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsTerminateSystemThread routine [Kernel-Mode Driver Architecture], PsTerminateSystemThread, k108_a8e19a60-578c-42a6-b77a-cf6c4098c815.xml, kernel.psterminatesystemthread, wdm/PsTerminateSystemThread
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsTerminateSystemThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PsTerminateSystemThread function


## -description


The <b>PsTerminateSystemThread</b> routine terminates the current system thread.


## -syntax


````
NTSTATUS PsTerminateSystemThread(
  _In_ NTSTATUS ExitStatus
);
````


## -parameters




### -param ExitStatus [in]

Specifies the status of the terminating system thread. 


## -returns



<b>PsTerminateSystemThread</b> does not return if it successfully terminates the calling thread. If the routine cannot terminate the thread (for example, if the thread is not a system thread), the routine returns an error NTSTATUS value. 




## -remarks



A system thread calls <b>PsTerminateSystemThread</b> to terminate itself. A driver that creates its own threads must ensure that each such thread terminates. The driver must not terminate any threads that the system or other drivers created. 




## -see-also

<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsTerminateSystemThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

