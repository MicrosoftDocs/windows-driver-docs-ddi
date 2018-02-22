---
UID: NF:ks.KsSetDefaultClockTime
title: KsSetDefaultClockTime function
author: windows-driver-content
description: The KsSetDefaultClockTime function sets the current time of the clock.
old-location: stream\kssetdefaultclocktime.htm
old-project: stream
ms.assetid: c8b4fef4-cfbb-4cdd-b762-062b8ae4a423
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KsSetDefaultClockTime, stream.kssetdefaultclocktime, KsSetDefaultClockTime, KsSetDefaultClockTime function [Streaming Media Devices], ksfunc_737648d0-8fc4-405c-96c8-61778e6758e9.xml
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
-	KsSetDefaultClockTime
product: Windows
targetos: Windows
req.typenames: 
---

# KsSetDefaultClockTime function


## -description


The <b>KsSetDefaultClockTime</b> function sets the current time of the clock. It modifies the current time returned by the clock. The owner of the default clock is expected to serialize access to this function and to the <a href="..\ks\nf-ks-kssetdefaultclockstate.md">KsSetDefaultClockState</a> function.

The function can be called at DISPATCH_LEVEL.


## -syntax


````
VOID KsSetDefaultClockTime(
  _In_ PKSDEFAULTCLOCK DefaultClock,
  _In_ LONGLONG        Time
);
````


## -parameters




### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among instances of the default clock for the parent. 


### -param Time [in]

Specifies the new time to set the clock. 


## -returns



None




## -see-also

<a href="..\ks\nf-ks-ksgetdefaultclocktime.md">KsGetDefaultClockTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsSetDefaultClockTime function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

