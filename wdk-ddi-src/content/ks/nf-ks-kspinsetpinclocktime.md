---
UID: NF:ks.KsPinSetPinClockTime
title: KsPinSetPinClockTime function
author: windows-driver-content
description: The KsPinSetPinClockTime function sets the current time on the clock exposed by Pin.
old-location: stream\kspinsetpinclocktime.htm
old-project: stream
ms.assetid: 85dac103-c729-4202-96b1-661891c6a531
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinSetPinClockTime, KsPinSetPinClockTime function [Streaming Media Devices], avfunc_8f1c1b04-c5eb-4aa1-9cdf-84b86da388e9.xml, ks/KsPinSetPinClockTime, stream.kspinsetpinclocktime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinSetPinClockTime
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinSetPinClockTime function


## -description


The<b> KsPinSetPinClockTime </b>function sets the current time on the clock exposed by <i>Pin</i>.


## -syntax


````
VOID KsPinSetPinClockTime(
  _In_ PKSPIN   Pin,
  _In_ LONGLONG Time
);
````


## -parameters




### -param Pin [in]

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the AVStream pin object for which the exposed clock is set to the time specified by <i>Time</i>.


### -param Time [in]

This parameter specifies the time that is set on the clock exposed by <i>Pin</i>. To determine time measurement units, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff560732">IKsReferenceClock::GetResolution</a>.


## -returns



None




## -remarks



<b>KsPinSetPinClockTime </b>modifies the current time returned by the clock. If an external clock is used, this function can still be used to force a resetting of the current timer when the external timer is not being used. In this case, the time provided is ignored and must be set to zero.




## -see-also

<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>



<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>



<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>



<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a>



<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>



<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>



 

 


