---
UID: NC:ks.PFNKSPIN
title: PFNKSPIN
author: windows-driver-content
description: An AVStream minidriver's callback routine is called when:\_There is data available for a KSPIN structure to process. Use this routine to perform Pin-Centric Processing.The relevant KSPIN is serving as a sink pin and is connected to an AVStream source pin.
old-location: stream\avstrminipinprocess.htm
old-project: stream
ms.assetid: d2315dd9-1643-4b8e-a010-8fccc582ca2b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminipinprocess, AVStrMiniPinProcess, AVStrMiniPinConnect, MyAVStrMiniPin routine [Streaming Media Devices], MyAVStrMiniPin, PFNKSPIN, PFNKSPIN, ks/MyAVStrMiniPin, avstclbk_9c9fb1b9-d592-41de-8190-b8b2808ea35b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	MyAVStrMiniPin
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSPIN callback


## -description


An AVStream minidriver's callback routine is called when: 
<ul>
<li>There is data available for a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure to process. Use this routine to perform <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>.</li>
<li>The relevant <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> is serving as a sink pin and is connected to an AVStream source pin.</li>
</ul>

## -prototype


````
PFNKSPIN MyAVStrMiniPin;

NTSTATUS MyAVStrMiniPin(
  _In_ PKSPIN Pin
)
{ ... }
````


## -parameters




### -param Pin [in]

Pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> that has frame data available to process.


## -returns



Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event.




## -remarks



<b>About AVStrMiniPinProcess</b>

The minidriver specifies this routine's address in the <b>Process</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

Indicate that a filter uses <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a> by providing this dispatch function. The minidriver sets pin flags in the relevant <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a> structure that determine when AVStream calls <i>AVStrMiniPinProcess</i>. If the minidriver sets no flags in the descriptor, the default behavior is that AVStream calls <i>AVStrMiniPinProcess</i> when new data arrives into a previously empty queue. See Pin-Centric Processing for more details on processing triggers.

After processing, the minidriver can prevent the frame from being completed by cloning the leading edge stream pointer. To do this, call <a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>. See <a href="https://msdn.microsoft.com/73ab974f-8034-421f-980a-2393d84ec54c">Leading and Trailing Edge Stream Pointers</a>.

Alternatively, specify a distinct trailing edge by setting KSPIN_FLAG_DISTINCT_TRAILING_EDGE on <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>. A third option is not to advance the leading edge stream pointer.

The process dispatch is either made at the default IRQL = PASSIVE_LEVEL, or possibly at DISPATCH_LEVEL if the minidriver has specified KSPIN_FLAG_DISPATCH_LEVEL_PROCESSING in the relevant <a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>.

This routine is optional.

<b>About AVStrMiniPinConnect</b>

The minidriver specifies this routine's address in the <b>Connect</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

Return STATUS_SUCCESS or the error returned from the attempt to establish an intra-connection. Do not return STATUS_PENDING. 

This routine is optional.

Also see <a href="https://msdn.microsoft.com/04d0d17b-c326-417d-b2e8-58b33420455a">KS Pins</a>.




## -see-also

<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>



<a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>



<a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>



<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPIN routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

