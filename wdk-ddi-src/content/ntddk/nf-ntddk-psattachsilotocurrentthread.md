---
UID: NF:ntddk.PsAttachSiloToCurrentThread
title: PsAttachSiloToCurrentThread function
author: windows-driver-content
description: This routine places a thread temporarily into the specified Silo.
old-location: kernel\psattachsilotocurrentthread.htm
old-project: kernel
ms.assetid: 1C66E50F-3BD7-4038-9FDF-2F2B712D9B5E
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psattachsilotocurrentthread, PsAttachSiloToCurrentThread routine [Kernel-Mode Driver Architecture], ntddk/PsAttachSiloToCurrentThread, PsAttachSiloToCurrentThread
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
-	PsAttachSiloToCurrentThread
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# PsAttachSiloToCurrentThread function


## -description


This routine places a thread temporarily into the specified <i>Silo</i>.


## -syntax


````
PESILO PsAttachSiloToCurrentThread(
  _In_ PESILO Silo
);
````


## -parameters




### -param Silo [in]

The silo that the thread is to impersonate. The caller must hold a  reference to the silo throughout the duration of the impersonation.


## -returns



The previous silo that was attached to the current thread.




## -remarks



The specified <i>Silo</i> is attached to the current thread so that it becomes the effective silo for the thread.

The thread then operates within the namespace of the attached silo until <a href="..\ntddk\nf-ntddk-psdetachsilofromcurrentthread.md">PsDetachSiloFromCurrentThread</a> is called.


#### Examples

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>PESILO PreviousSilo = PsAttachSiloToCurrentThread();

// Do work within the silo context

PsDetachSiloFromCurrentThread(PreviousSilo);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\ntddk\nf-ntddk-psdetachsilofromcurrentthread.md">PsDetachSiloFromCurrentThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsAttachSiloToCurrentThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

