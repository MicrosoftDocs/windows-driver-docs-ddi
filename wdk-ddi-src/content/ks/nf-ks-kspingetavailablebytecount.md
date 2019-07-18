---
UID: NF:ks.KsPinGetAvailableByteCount
title: KsPinGetAvailableByteCount function (ks.h)
description: The KsPinGetAvailableByteCount routine outputs the number of bytes of input data ahead of the leading edge and the number of bytes of output buffer ahead of the leading edge, both for the queue of a caller-specified pin.
old-location: stream\kspingetavailablebytecount.htm
tech.root: stream
ms.assetid: e3669f11-7284-4f65-b814-624337e7fa7f
ms.date: 04/23/2018
ms.keywords: KsPinGetAvailableByteCount, KsPinGetAvailableByteCount routine [Streaming Media Devices], avfunc_2ba6a7f8-59b4-45bf-989a-97f8a494b4bc.xml, ks/KsPinGetAvailableByteCount, stream.kspingetavailablebytecount
ms.topic: function
f1_keywords:
 - "ks/KsPinGetAvailableByteCount"
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
- KsPinGetAvailableByteCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetAvailableByteCount function


## -description


The<b> KsPinGetAvailableByteCount</b> routine outputs the number of bytes of input data ahead of the leading edge and the number of bytes of output buffer ahead of the leading edge, both for the queue of a caller-specified pin.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> structure for which to calculate these queue parameters.


### -param InputDataBytes [out, optional]

A pointer to a LONG value in which the routine returns the number of input data bytes ahead of the leading edge. Caller sets to <b>NULL</b> if this value is not requested.


### -param OutputBufferBytes [out, optional]

A pointer to  a LONG value in which the routine returns the number of output buffer bytes ahead of the leading edge. Caller sets to <b>NULL</b> if this value is not requested.


## -returns



Returns STATUS_SUCCESS if the requested count(s) have been retrieved. A nonsuccessful return status indicates that <i>Pin</i> does not have an associated queue.




## -remarks



Noninplace pins should use <i>InputDataBytes</i> for input pins and <i>OutputBufferBytes</i> for output pins.

The results of this call are not guaranteed to be safe unless either the processing mutex is held at call-time, or the caller has privately synchronized before calling the routine. To private synchronize, ensure that the pin does not transition from Acquire to Stop while the routine is executing. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/processing-mutex-in-avstream">Processing Mutex in AVStream</a>.

Also note that in-place transform can supply input and output counts.

In Windows XP and DirectX 8.0, the <i>InputDataBytes</i> count is not valid unless frames that the filter receives are full.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/leading-and-trailing-edge-stream-pointers">Leading and Trailing Edge Stream Pointers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspin">AVStrMiniPinProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfilteracquireprocessingmutex">KsFilterAcquireProcessingMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfilterreleaseprocessingmutex">KsFilterReleaseProcessingMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinacquireprocessingmutex">KsPinAcquireProcessingMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetleadingedgestreampointer">KsPinGetLeadingEdgeStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingettrailingedgestreampointer">KsPinGetTrailingEdgeStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinreleaseprocessingmutex">KsPinReleaseProcessingMutex</a>
 

 

