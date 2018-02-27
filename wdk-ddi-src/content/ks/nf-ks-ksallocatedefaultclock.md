---
UID: NF:ks.KsAllocateDefaultClock
title: KsAllocateDefaultClock function
author: windows-driver-content
description: The KsAllocateDefaultClock function allocates and initializes the default clock structure.
old-location: stream\ksallocatedefaultclock.htm
old-project: stream
ms.assetid: 5ba14903-1519-4edd-bc3c-a05cb040652d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsAllocateDefaultClock, KsAllocateDefaultClock function [Streaming Media Devices], ks/KsAllocateDefaultClock, ksfunc_448f966b-08aa-4ac5-92db-36d923275754.xml, stream.ksallocatedefaultclock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsAllocateDefaultClock
product: Windows
targetos: Windows
req.typenames: 
---

# KsAllocateDefaultClock function


## -description


The <b>KsAllocateDefaultClock</b> function allocates and initializes the default clock structure.


## -syntax


````
NTSTATUS KsAllocateDefaultClock(
  _Out_ PKSDEFAULTCLOCK *DefaultClock
);
````


## -parameters




### -param DefaultClock [out]

Specifies the caller-allocated shared default clock structure. The current time is set to zero and the state is set to KSSTATE_STOP. Upon successful completion of this routine, the structure indicated by this pointer will contain a reference to the default clock. The data returned should be treated as opaque and reserved for system use.


## -returns



The <b>KsAllocateDefaultClock</b> function returns STATUS_SUCCESS if successful, or a memory error if unsuccessful.




## -remarks



The internal DefaultClock.ReferenceCount element is initialized to one by the <b>KsAllocateDefaultClock</b> function. The element is incremented and decremented as each notification DPC is queued and completed. When the structure is to be freed, the element is used to determine if the owner of the clock should free the structure or if a pending DPC should free it asynchronously.

When the clock is no longer needed, the driver must call <a href="..\ks\nf-ks-ksfreedefaultclock.md">KsFreeDefaultClock</a> to release any resources allocated for use with the clock.




## -see-also

<a href="..\ks\nf-ks-ksfreedefaultclock.md">KsFreeDefaultClock</a>



<a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAllocateDefaultClock function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

