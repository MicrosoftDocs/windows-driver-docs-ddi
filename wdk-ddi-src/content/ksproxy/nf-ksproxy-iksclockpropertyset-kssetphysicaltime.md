---
UID: NF:ksproxy.IKsClockPropertySet.KsSetPhysicalTime
title: IKsClockPropertySet::KsSetPhysicalTime method
author: windows-driver-content
description: The KsSetPhysicalTime method sets the physical time on the underlying clock.
old-location: stream\iksclockpropertyset_kssetphysicaltime.htm
old-project: stream
ms.assetid: 2f8eb011-1fe1-40f6-b833-50d3e853bffd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsClockPropertySet::KsSetPhysicalTime, KsSetPhysicalTime method [Streaming Media Devices], KsSetPhysicalTime method [Streaming Media Devices], IKsClockPropertySet interface, KsSetPhysicalTime, IKsClockPropertySet, ksproxy/IKsClockPropertySet::KsSetPhysicalTime, IKsClockPropertySet interface [Streaming Media Devices], KsSetPhysicalTime method, ksproxy_1cebc4eb-efb8-4ec6-97f4-e34fc978fb2f.xml, stream.iksclockpropertyset_kssetphysicaltime
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsClockPropertySet.KsSetPhysicalTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsClockPropertySet::KsSetPhysicalTime method


## -description


The <b>KsSetPhysicalTime</b> method sets the physical time on the underlying clock. 


## -syntax


````
HRESULT KsSetPhysicalTime(
  [in] LONGLONG Time
);
````


## -parameters




### -param Time [in]

Physical time to which to set the underlying clock.


## -returns


Returns NOERROR if successful; otherwise, returns an error code.



## -remarks


The physical time is based on some underlying physical clock that always progresses, even if the physical type of clock must be changed on the fly. Other physical clocks use an underlying clock's physical time for rate matching.

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a> property to set the physical time. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559742">IKsClockPropertySet::KsGetPhysicalTime</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsSetPhysicalTime method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

