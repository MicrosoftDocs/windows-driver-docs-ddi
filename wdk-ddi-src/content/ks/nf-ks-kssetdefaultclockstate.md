---
UID: NF:ks.KsSetDefaultClockState
title: KsSetDefaultClockState function
author: windows-driver-content
description: The KsSetDefaultClockState function sets the current state of the clock that is used to reflect the current state of the underlying filter pin.
old-location: stream\kssetdefaultclockstate.htm
old-project: stream
ms.assetid: 5893f4ff-0eb5-4cdc-8f58-f7654c1ce9fc
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KsSetDefaultClockState, KsSetDefaultClockState function [Streaming Media Devices], ksfunc_a57f26f0-cd4a-4d80-a090-788aef1ccf4b.xml, stream.kssetdefaultclockstate, ks/KsSetDefaultClockState
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
-	KsSetDefaultClockState
product: Windows
targetos: Windows
req.typenames: 
---

# KsSetDefaultClockState function


## -description


The <b>KsSetDefaultClockState</b> function sets the current state of the clock that is used to reflect the current state of the underlying filter pin. The owner of the default clock is expected to serialize access to this function and to call <a href="..\ks\nf-ks-kssetdefaultclocktime.md">KsSetDefaultClockTime</a>.

The function can be called at DISPATCH_LEVEL.


## -syntax


````
VOID KsSetDefaultClockState(
  _In_ PKSDEFAULTCLOCK DefaultClock,
  _In_ KSSTATE         State
);
````


## -parameters




### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent.


### -param State [in]

Specifies the new state to set the clock.


## -returns



None




## -see-also

<a href="..\ks\nf-ks-ksgetdefaultclockstate.md">KsGetDefaultClockState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsSetDefaultClockState function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

