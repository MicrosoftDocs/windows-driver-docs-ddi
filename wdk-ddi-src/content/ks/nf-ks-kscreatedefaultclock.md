---
UID: NF:ks.KsCreateDefaultClock
title: KsCreateDefaultClock function
author: windows-driver-content
description: Given an IRP_MJ_CREATE request, the KsCreateDefaultClock function creates a default clock that uses the system clock as a time base and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the clock using an internal dispatch table (KSDISPATCH_TABLE). Does not complete the IRP or set the status in the IRP.The KsCreateDefaultClock function can only be called at PASSIVE_LEVEL.
old-location: stream\kscreatedefaultclock.htm
old-project: stream
ms.assetid: 38ac85bc-9ace-4e70-a886-92e18afb32db
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsCreateDefaultClock, stream.kscreatedefaultclock, KsCreateDefaultClock function [Streaming Media Devices], ksfunc_eb8617e1-d6e0-434d-bace-cec6b2b1cce1.xml, KsCreateDefaultClock
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsCreateDefaultClock
product: Windows
targetos: Windows
req.typenames: 
---

# KsCreateDefaultClock function


## -description


Given an IRP_MJ_CREATE request, the <b>KsCreateDefaultClock</b> function creates a default clock that uses the system clock as a time base and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the clock using an internal dispatch table (KSDISPATCH_TABLE).  Does not complete the IRP or set the status in the IRP.

The <b>KsCreateDefaultClock</b> function can only be called at PASSIVE_LEVEL.


## -syntax


````
NTSTATUS KsCreateDefaultClock(
  _In_ PIRP            Irp,
  _In_ PKSDEFAULTCLOCK DefaultClock
);
````


## -parameters




### -param Irp [in]

Specifies the IRP with the clock-create request being handled.


### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent.


## -returns


The <b>KsCreateDefaultClock</b> function returns STATUS_SUCCESS if successful, or an error if unsuccessful.



## -remarks


The clock can be created after using <b>KsAllocateDefaultClock</b> to create and initialize the internal structures for a default clock instance. After initialization, many file objects can be created against the same underlying default clock instance.



## -see-also

<a href="..\ks\nf-ks-ksallocatedefaultclock.md">KsAllocateDefaultClock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateDefaultClock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

