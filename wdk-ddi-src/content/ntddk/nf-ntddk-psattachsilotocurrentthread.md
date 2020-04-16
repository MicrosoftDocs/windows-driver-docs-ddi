---
UID: NF:ntddk.PsAttachSiloToCurrentThread
title: PsAttachSiloToCurrentThread function (ntddk.h)
description: This routine places a thread temporarily into the specified Silo.
old-location: kernel\psattachsilotocurrentthread.htm
tech.root: kernel
ms.assetid: 1C66E50F-3BD7-4038-9FDF-2F2B712D9B5E
ms.date: 04/30/2018
keywords: ["PsAttachSiloToCurrentThread function"]
ms.keywords: PsAttachSiloToCurrentThread, PsAttachSiloToCurrentThread routine [Kernel-Mode Driver Architecture], kernel.psattachsilotocurrentthread, ntddk/PsAttachSiloToCurrentThread
f1_keywords:
 - "ntddk/PsAttachSiloToCurrentThread"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- PsAttachSiloToCurrentThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsAttachSiloToCurrentThread function


## -description


This routine places a thread temporarily into the specified <i>Silo</i>.


## -parameters




### -param Silo [in]

The silo that the thread is to impersonate. The caller must hold a  reference to the silo throughout the duration of the impersonation.


## -returns



The previous silo that was attached to the current thread.




## -remarks



The specified <i>Silo</i> is attached to the current thread so that it becomes the effective silo for the thread.

The thread then operates within the namespace of the attached silo until <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psdetachsilofromcurrentthread">PsDetachSiloFromCurrentThread</a> is called.


#### Examples

```cpp
PESILO PreviousSilo = PsAttachSiloToCurrentThread(SomeSilo);

// Do work within the silo context

PsDetachSiloFromCurrentThread(PreviousSilo);</pre>
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psdetachsilofromcurrentthread">PsDetachSiloFromCurrentThread</a>
 

 

