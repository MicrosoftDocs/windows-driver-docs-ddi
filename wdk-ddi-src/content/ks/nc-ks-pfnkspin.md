---
UID: NC:ks.PFNKSPIN
title: PFNKSPIN (ks.h)
description: An AVStream minidriver's callback routine is called when:\_There is data available for a KSPIN structure to process. Use this routine to perform Pin-Centric Processing.The relevant KSPIN is serving as a sink pin and is connected to an AVStream source pin.
old-location: stream\avstrminipinprocess.htm
tech.root: stream
ms.assetid: d2315dd9-1643-4b8e-a010-8fccc582ca2b
ms.date: 04/23/2018
keywords: ["PFNKSPIN callback function"]
ms.keywords: AVStrMiniPinConnect, AVStrMiniPinProcess, MyAVStrMiniPin, MyAVStrMiniPin routine [Streaming Media Devices], PFNKSPIN, avstclbk_9c9fb1b9-d592-41de-8190-b8b2808ea35b.xml, ks/MyAVStrMiniPin, stream.avstrminipinprocess
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSPIN
 - ks/PFNKSPIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - MyAVStrMiniPin
---

# PFNKSPIN callback function


## -description

An AVStream minidriver's callback routine is called when: 
<ul>
<li>There is data available for a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure to process. Use this routine to perform <a href="/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a>.</li>
<li>The relevant <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> is serving as a sink pin and is connected to an AVStream source pin.</li>
</ul>

## -parameters

### -param Pin 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> that has frame data available to process.

## -returns

Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event.

## -remarks

<b>About AVStrMiniPinProcess</b>

The minidriver specifies this routine's address in the <b>Process</b> member of its <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure.

Indicate that a filter uses <a href="/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a> by providing this dispatch function. The minidriver sets pin flags in the relevant <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a> structure that determine when AVStream calls <i>AVStrMiniPinProcess</i>. If the minidriver sets no flags in the descriptor, the default behavior is that AVStream calls <i>AVStrMiniPinProcess</i> when new data arrives into a previously empty queue. See Pin-Centric Processing for more details on processing triggers.

After processing, the minidriver can prevent the frame from being completed by cloning the leading edge stream pointer. To do this, call <a href="/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>. See <a href="/windows-hardware/drivers/stream/leading-and-trailing-edge-stream-pointers">Leading and Trailing Edge Stream Pointers</a>.

Alternatively, specify a distinct trailing edge by setting KSPIN_FLAG_DISTINCT_TRAILING_EDGE on <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>. A third option is not to advance the leading edge stream pointer.

The process dispatch is either made at the default IRQL = PASSIVE_LEVEL, or possibly at DISPATCH_LEVEL if the minidriver has specified KSPIN_FLAG_DISPATCH_LEVEL_PROCESSING in the relevant <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>.

This routine is optional.

<b>About AVStrMiniPinConnect</b>

The minidriver specifies this routine's address in the <b>Connect</b> member of its <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure.

Return STATUS_SUCCESS or the error returned from the attempt to establish an intra-connection. Do not return STATUS_PENDING. 

This routine is optional.

Also see <a href="/windows-hardware/drivers/stream/ks-pins">KS Pins</a>.

## -see-also

<a href="/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>



<a href="/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>



<a href="/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a>