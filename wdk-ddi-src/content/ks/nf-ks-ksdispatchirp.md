---
UID: NF:ks.KsDispatchIrp
title: KsDispatchIrp function (ks.h)
description: KsDispatchIrp calls a dispatch routine corresponding to the function code of the specified IRP. KsDispatchIrp then returns the status code from this call.
old-location: stream\ksdispatchirp.htm
tech.root: stream
ms.assetid: 6ee88b2d-4086-4e6d-b80b-eff6868ce784
ms.date: 04/23/2018
ms.keywords: KsDispatchIrp, KsDispatchIrp routine [Streaming Media Devices], ks/KsDispatchIrp, ksfunc_ed03b195-fcb3-41ca-9794-c9b9f04ce8c9.xml, stream.ksdispatchirp
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsDispatchIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDispatchIrp function


## -description


<b>KsDispatchIrp</b> calls a dispatch routine corresponding to the function code of the specified IRP. <b>KsDispatchIrp</b> then returns the status code from this call.


## -parameters




### -param DeviceObject [in]

Specifies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> to which the specific file object belongs.


### -param Irp [in]

Contains the IRP for which to call a dispatch routine.


## -returns



Returns the status code returned from the dispatch routine.




## -remarks



A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561723">KSDISPATCH_TABLE</a> can be contained in the stack location's file object's <b>FsContext</b> member. <b>KsDispatchIrp</b> calls the dispatch routine listed in this dispatch table for that major code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566840">KsSetMajorFunctionHandler</a>
 

 

