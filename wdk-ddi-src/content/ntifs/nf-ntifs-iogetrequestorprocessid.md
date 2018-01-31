---
UID: NF:ntifs.IoGetRequestorProcessId
title: IoGetRequestorProcessId function
author: windows-driver-content
description: The IoGetRequestorProcessId routine returns the unique 32-bit process ID for the thread that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorprocessid.htm
old-project: ifsk
ms.assetid: 73fe40ee-f1fe-419b-a866-6c40604f7716
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/IoGetRequestorProcessId, IoGetRequestorProcessId routine [Installable File System Drivers], ifsk.iogetrequestorprocessid, ioref_a08b37d7-b999-4e40-a0aa-c62744fee6dd.xml, IoGetRequestorProcessId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
-	IoGetRequestorProcessId
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetRequestorProcessId function


## -description


The <b>IoGetRequestorProcessId</b> routine returns the unique 32-bit process ID for the thread that originally requested a given I/O operation.


## -syntax


````
ULONG IoGetRequestorProcessId(
  _In_ PIRP Irp
);
````


## -parameters




#### - Irp [in]

A pointer to the I/O request packet (IRP) for the specified I/O operation.


## -returns


<b>IoGetRequestorProcessId</b> returns the process ID for the thread that requested the I/O operation. If the IRP is not associated with any thread, <b>IoGetRequestorProcessId</b> returns zero.



## -remarks


On Microsoft Windows XP and later, <b>IoGetRequestorProcessId</b> returns the process ID for the process to which the thread is currently attached. 

On Microsoft Windows 2000 and earlier, <b>IoGetRequestorProcessId</b> returns the process ID for the process that created the thread. 

For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-iogetrequestorprocess.md">IoGetRequestorProcess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetRequestorProcessId routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

