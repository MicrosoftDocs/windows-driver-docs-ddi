---
UID: NF:ksproxy.IKsClockPropertySet.KsGetTime
title: IKsClockPropertySet::KsGetTime method
author: windows-driver-content
description: The KsGetTime method retrieves the time of the underlying clock.
old-location: stream\iksclockpropertyset_ksgettime.htm
old-project: stream
ms.assetid: 0d22baeb-d08f-4554-9af4-dae9480a471a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices], KsGetTime method, stream.iksclockpropertyset_ksgettime, KsGetTime method [Streaming Media Devices], IKsClockPropertySet interface, IKsClockPropertySet, ksproxy/IKsClockPropertySet::KsGetTime, KsGetTime, IKsClockPropertySet::KsGetTime, KsGetTime method [Streaming Media Devices], ksproxy_056c73f0-b713-4f86-a38c-a3455e33b773.xml
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
-	IKsClockPropertySet.KsGetTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsClockPropertySet::KsGetTime method


## -description


The <b>KsGetTime</b> method retrieves the time of the underlying clock. 


## -syntax


````
HRESULT KsGetTime(
  [out] LONGLONG *Time
);
````


## -parameters




### -param Time [out]

Pointer to a variable that receives the current clock time.


## -returns


Returns NOERROR if successful; otherwise, returns an error code.



## -remarks


The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559763">IKsClockPropertySet::KsSetTime</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsGetTime method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

