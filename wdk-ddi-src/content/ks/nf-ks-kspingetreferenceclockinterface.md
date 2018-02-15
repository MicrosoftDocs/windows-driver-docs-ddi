---
UID: NF:ks.KsPinGetReferenceClockInterface
title: KsPinGetReferenceClockInterface function
author: windows-driver-content
description: The KsPinGetReferenceClockInterface function returns a COM style interface to the reference clock associated with Pin. This interface pointer will be an IKsReferenceClock interface.
old-location: stream\kspingetreferenceclockinterface.htm
old-project: stream
ms.assetid: 49c78b4e-aa3a-4c4b-8720-0302a537c84c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPinGetReferenceClockInterface function [Streaming Media Devices], KsPinGetReferenceClockInterface, ks/KsPinGetReferenceClockInterface, avfunc_7434698b-f441-4d80-91db-8fa5d7d10c60.xml, stream.kspingetreferenceclockinterface
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinGetReferenceClockInterface
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetReferenceClockInterface function


## -description


The<b> KsPinGetReferenceClockInterface</b> function returns a COM style interface to the reference clock associated with <i>Pin</i>. This interface pointer will be an <b>IKsReferenceClock</b> interface.


## -syntax


````
NTSTATUS KsPinGetReferenceClockInterface(
  _In_  PKSPIN             Pin,
  _Out_ PIKSREFERENCECLOCK *Interface
);
````


## -parameters




### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to return the reference clock interface.


### -param Interface [out]

A pointer to a memory location that receives the address of an <a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a> interface. This is a COM style interface with an associated reference count. Minidrivers must release the interface when finished with it.


## -returns



<b>KsPinGetReferenceClockInterface</b> returns STATUS_SUCCESS and deposits the address of the  <a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a> interface into <i>Interface</i> if the pin implements the clock or has received notification of the master clock through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565713">KSPROPERTY_STREAM_MASTERCLOCK</a> property. Returns STATUS_DEVICE_NOT_READY if the pin has not yet received notification of the master clock.




## -remarks



The most common time to call <b>KsPinGetReferenceClockInterface</b> is in a state transition to KSSTATE_ACQUIRE.

See <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a> for more information about using the <a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a> interface that this routine returns.




## -see-also

<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>



<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>



<a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a>



<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>



<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="..\ks\nf-ks-kspinsetpinclocktime.md">KsPinSetPinClockTime</a>



<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetReferenceClockInterface function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

