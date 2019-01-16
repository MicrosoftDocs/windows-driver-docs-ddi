---
UID: NF:ntddk.PsDetachSiloFromCurrentThread
title: PsDetachSiloFromCurrentThread function
description: This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the PsAttachSiloToCurrentThread routine.
old-location: kernel\psdetachsilofromcurrentthread.htm
tech.root: kernel
ms.assetid: E364130B-9709-4FD9-8654-9FBC52E29145
ms.date: 04/30/2018
ms.keywords: PsDetachSiloFromCurrentThread, PsDetachSiloFromCurrentThread routine [Kernel-Mode Driver Architecture], kernel.psdetachsilofromcurrentthread, ntddk/PsDetachSiloFromCurrentThread
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsDetachSiloFromCurrentThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsDetachSiloFromCurrentThread function


## -description


This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt735057">PsAttachSiloToCurrentThread</a> routine.



<div class="alert"><b>Note</b>  The caller is responsible for dereferencing the object after the detach has completed.</div>
<div> </div>



## -parameters




### -param PreviousSilo [in]

The value returned from the silo attach call.


## -returns



This routine does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt735057">PsAttachSiloToCurrentThread</a>
 

 

