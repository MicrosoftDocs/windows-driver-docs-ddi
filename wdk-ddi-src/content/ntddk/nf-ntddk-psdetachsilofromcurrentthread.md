---
UID: NF:ntddk.PsDetachSiloFromCurrentThread
title: PsDetachSiloFromCurrentThread function
author: windows-driver-content
description: This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the PsAttachSiloToCurrentThread routine.
old-location: kernel\psdetachsilofromcurrentthread.htm
old-project: kernel
ms.assetid: E364130B-9709-4FD9-8654-9FBC52E29145
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psdetachsilofromcurrentthread, PsDetachSiloFromCurrentThread, ntddk/PsDetachSiloFromCurrentThread, PsDetachSiloFromCurrentThread routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsDetachSiloFromCurrentThread
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsDetachSiloFromCurrentThread function


## -description


This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the  <a href="..\ntddk\nf-ntddk-psattachsilotocurrentthread.md">PsAttachSiloToCurrentThread</a> routine.



<div class="alert"><b>Note</b>  The caller is responsible for dereferencing the object after the detach has completed.</div>
<div> </div>



## -syntax


````
void PsDetachSiloFromCurrentThread(
  _In_ PESILO PreviousSilo
);
````


## -parameters




### -param PreviousSilo [in]

The value returned from the silo attach call.


## -returns


This routine does not return a value.



## -see-also

<a href="..\ntddk\nf-ntddk-psattachsilotocurrentthread.md">PsAttachSiloToCurrentThread</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsDetachSiloFromCurrentThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

