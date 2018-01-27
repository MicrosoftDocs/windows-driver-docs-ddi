---
UID: NF:ks.KsPinSetPinClockTime
title: KsPinSetPinClockTime function
author: windows-driver-content
description: The KsPinSetPinClockTime function sets the current time on the clock exposed by Pin.
old-location: stream\kspinsetpinclocktime.htm
old-project: stream
ms.assetid: 85dac103-c729-4202-96b1-661891c6a531
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kspinsetpinclocktime, avfunc_8f1c1b04-c5eb-4aa1-9cdf-84b86da388e9.xml, ks/KsPinSetPinClockTime, KsPinSetPinClockTime function [Streaming Media Devices], KsPinSetPinClockTime
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ks.lib
-	Ks.dll
apiname: 
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

<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>

<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>

<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>

<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>

<a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a>

<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>

<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>

<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinSetPinClockTime function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

