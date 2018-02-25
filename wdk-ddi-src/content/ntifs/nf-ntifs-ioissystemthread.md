---
UID: NF:ntifs.IoIsSystemThread
title: IoIsSystemThread function
author: windows-driver-content
description: The IoIsSystemThread routine checks whether a given thread is a system thread.
old-location: ifsk\ioissystemthread.htm
old-project: ifsk
ms.assetid: 1f3dc15f-14b5-4797-83be-ba3a01a1551b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , I, IoIsSystemThread, IoIsSystemThread routine [Installable File System Drivers], S, T, a, d, e, h, ifsk.ioissystemthread, ioref_3e14f3af-c985-43a4-bc57-927483597c79.xml, m, ntifs/IoIsSystemThread, o, r, s, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoIsSystemThread
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoIsSystemThread function


## -description


The <b>IoIsSystemThread</b> routine checks whether a given thread is a system thread. 


## -syntax


````
BOOLEAN IoIsSystemThread(
  _In_ PETHREAD Thread
);
````


## -parameters




### -param Thread [in]

Pointer to the thread to be checked. 


## -returns



<b>IoIsSystemThread</b> returns <b>TRUE</b> if the specified thread is a system thread, otherwise <b>FALSE</b>. 




## -remarks



For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-psissystemthread.md">PsIsSystemThread</a>



<a href="..\ntddk\nf-ntddk-psgetcurrentthread.md">PsGetCurrentThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoIsSystemThread routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

