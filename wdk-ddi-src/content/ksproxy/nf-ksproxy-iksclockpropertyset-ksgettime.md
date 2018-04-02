---
UID: NF:ksproxy.IKsClockPropertySet.KsGetTime
title: IKsClockPropertySet::KsGetTime method
author: windows-driver-content
description: The KsGetTime method retrieves the time of the underlying clock.
old-location: stream\iksclockpropertyset_ksgettime.htm
old-project: stream
ms.assetid: 0d22baeb-d08f-4554-9af4-dae9480a471a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], KsGetTime method, IKsClockPropertySet::KsGetTime, KsGetTime method [Streaming Media Devices], KsGetTime method [Streaming Media Devices], IKsClockPropertySet interface, KsGetTime,IKsClockPropertySet.KsGetTime, ksproxy/IKsClockPropertySet::KsGetTime, ksproxy_056c73f0-b713-4f86-a38c-a3455e33b773.xml, stream.iksclockpropertyset_ksgettime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsClockPropertySet.KsGetTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsClockPropertySet::KsGetTime method


## -description


The <b>KsGetTime</b> method retrieves the time of the underlying clock. 


## -parameters




### -param Time [out]

Pointer to a variable that receives the current clock time.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559763">IKsClockPropertySet::KsSetTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a>
 

 

