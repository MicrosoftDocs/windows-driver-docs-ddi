---
UID: NC:ks.PFNKSPIN
title: PFNKSPIN
description: An AVStream minidriver's callback routine is called when:\_There is data available for a KSPIN structure to process. Use this routine to perform Pin-Centric Processing.The relevant KSPIN is serving as a sink pin and is connected to an AVStream source pin.
old-location: stream\avstrminipinprocess.htm
tech.root: stream
ms.assetid: d2315dd9-1643-4b8e-a010-8fccc582ca2b
ms.date: 04/23/2018
ms.keywords: AVStrMiniPinConnect, AVStrMiniPinProcess, MyAVStrMiniPin, MyAVStrMiniPin routine [Streaming Media Devices], PFNKSPIN, avstclbk_9c9fb1b9-d592-41de-8190-b8b2808ea35b.xml, ks/MyAVStrMiniPin, stream.avstrminipinprocess
ms.topic: callback
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
req.irql: "(See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	MyAVStrMiniPin
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSPIN callback function


## -description


An AVStream minidriver's callback routine is called when: 
<ul>
<li>There is data available for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure to process. Use this routine to perform <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>.</li>
<li>The relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> is serving as a sink pin and is connected to an AVStream source pin.</li>
</ul>

## -parameters




### -param Pin [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> that has frame data available to process.


## -returns



Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event.




## -remarks



<b>About AVStrMiniPinProcess</b>

The minidriver specifies this routine's address in the <b>Process</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a> structure.

Indicate that a filter uses <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a> by providing this dispatch function. The minidriver sets pin flags in the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a> structure that determine when AVStream calls <i>AVStrMiniPinProcess</i>. If the minidriver sets no flags in the descriptor, the default behavior is that AVStream calls <i>AVStrMiniPinProcess</i> when new data arrives into a previously empty queue. See Pin-Centric Processing for more details on processing triggers.

After processing, the minidriver can prevent the frame from being completed by cloning the leading edge stream pointer. To do this, call <a href="https://msdn.microsoft.com/library/windows/hardware/dn892389">KsStreamPointerClone</a>. See <a href="https://msdn.microsoft.com/73ab974f-8034-421f-980a-2393d84ec54c">Leading and Trailing Edge Stream Pointers</a>.

Alternatively, specify a distinct trailing edge by setting KSPIN_FLAG_DISTINCT_TRAILING_EDGE on <a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>. A third option is not to advance the leading edge stream pointer.

The process dispatch is either made at the default IRQL = PASSIVE_LEVEL, or possibly at DISPATCH_LEVEL if the minidriver has specified KSPIN_FLAG_DISPATCH_LEVEL_PROCESSING in the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>.

This routine is optional.

<b>About AVStrMiniPinConnect</b>

The minidriver specifies this routine's address in the <b>Connect</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a> structure.

Return STATUS_SUCCESS or the error returned from the attempt to establish an intra-connection. Do not return STATUS_PENDING. 

This routine is optional.

Also see <a href="https://msdn.microsoft.com/04d0d17b-c326-417d-b2e8-58b33420455a">KS Pins</a>.




## -see-also




<a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892389">KsStreamPointerClone</a>



<a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>
 

 

