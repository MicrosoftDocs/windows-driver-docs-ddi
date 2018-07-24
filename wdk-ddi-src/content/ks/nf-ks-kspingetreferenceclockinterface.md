---
UID: NF:ks.KsPinGetReferenceClockInterface
title: KsPinGetReferenceClockInterface function
author: windows-driver-content
description: The KsPinGetReferenceClockInterface function returns a COM style interface to the reference clock associated with Pin. This interface pointer will be an IKsReferenceClock interface.
old-location: stream\kspingetreferenceclockinterface.htm
tech.root: stream
ms.assetid: 49c78b4e-aa3a-4c4b-8720-0302a537c84c
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsPinGetReferenceClockInterface, KsPinGetReferenceClockInterface function [Streaming Media Devices], avfunc_7434698b-f441-4d80-91db-8fa5d7d10c60.xml, ks/KsPinGetReferenceClockInterface, stream.kspingetreferenceclockinterface
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinGetReferenceClockInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetReferenceClockInterface function


## -description


The<b> KsPinGetReferenceClockInterface</b> function returns a COM style interface to the reference clock associated with <i>Pin</i>. This interface pointer will be an <b>IKsReferenceClock</b> interface.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which to return the reference clock interface.


### -param Interface [out]

A pointer to a memory location that receives the address of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560725">IKsReferenceClock</a> interface. This is a COM style interface with an associated reference count. Minidrivers must release the interface when finished with it.


## -returns



<b>KsPinGetReferenceClockInterface</b> returns STATUS_SUCCESS and deposits the address of the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560725">IKsReferenceClock</a> interface into <i>Interface</i> if the pin implements the clock or has received notification of the master clock through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565713">KSPROPERTY_STREAM_MASTERCLOCK</a> property. Returns STATUS_DEVICE_NOT_READY if the pin has not yet received notification of the master clock.




## -remarks



The most common time to call <b>KsPinGetReferenceClockInterface</b> is in a state transition to KSSTATE_ACQUIRE.

See <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a> for more information about using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560725">IKsReferenceClock</a> interface that this routine returns.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559766">IKsControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560725">IKsReferenceClock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562547">KsFilterGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562655">KsGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563506">KsPinGetConnectedFilterInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563509">KsPinGetConnectedPinInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563528">KsPinSetPinClockTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>
 

 

