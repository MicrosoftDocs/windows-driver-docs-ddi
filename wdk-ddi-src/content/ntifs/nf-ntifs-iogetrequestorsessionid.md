---
UID: NF:ntifs.IoGetRequestorSessionId
title: IoGetRequestorSessionId function
author: windows-driver-content
description: The IoGetRequestorSessionId routine returns the session ID for the process that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorsessionid.htm
old-project: ifsk
ms.assetid: 9e13cf62-d71e-4878-becd-d34beb2f59b3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , G, I, IoGetRequestorSessionId, IoGetRequestorSessionId routine [Installable File System Drivers], R, S, d, e, i, ifsk.iogetrequestorsessionid, ioref_fe60ee3b-1b5b-4d9c-a4f2-456e05575349.xml, n, ntifs/IoGetRequestorSessionId, o, q, r, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows Server 2003 SP1 and later.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetRequestorSessionId
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoGetRequestorSessionId function


## -description


The <b>IoGetRequestorSessionId</b> routine returns the session ID for the process that originally requested a given I/O operation.


## -syntax


````
NTSTATUS IoGetRequestorSessionId(
  _In_  PIRP   Irp,
  _Out_ PULONG pSessionId
);
````


## -parameters




### -param Irp [in]

A pointer to the I/O request packet (IRP) for the I/O operation. 


### -param pSessionId [out]

A pointer to a caller-allocated variable that receives the session ID for the process that requested the I/O operation. If the call to <a href="..\ntifs\nf-ntifs-iogetrequestorprocessid.md">IoGetRequestorProcessId</a> fails, this variable is set to -1.


## -returns




<a href="..\ntifs\nf-ntifs-iogetrequestorprocessid.md">IoGetRequestorProcessId</a> returns STATUS_SUCCESS if the session ID is successfully returned, STATUS_UNSUCCESSFUL otherwise. STATUS_UNSUCCESSFUL is an error NTSTATUS value. 




## -see-also

<a href="..\ntifs\nf-ntifs-iogetrequestorprocess.md">IoGetRequestorProcess</a>



<a href="..\ntifs\nf-ntifs-iogetrequestorprocessid.md">IoGetRequestorProcessId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetRequestorSessionId routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

