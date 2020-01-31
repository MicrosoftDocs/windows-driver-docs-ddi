---
UID: NC:ks.PFNKSPINVOID
title: PFNKSPINVOID (ks.h)
description: An AVStream minidriver's callback routine is called when:The relevant KSPIN is serving as a sink pin and this sink pin is disconnected from an AVStream source pin.A KSPIN structure's reset state is changed due to the arrival of an IOCTL_KS_RESET_STATE device control. This routine is also called when the queue associated with the given pin is flushed.
old-location: stream\avstrminipindisconnect.htm
tech.root: stream
ms.assetid: 64bcbc05-8dbd-4f97-afbb-dadd44b60078
ms.date: 04/23/2018
ms.keywords: AVStrMiniPinDisconnect, AVStrMiniPinReset, MyAVStrMiniPin, MyAVStrMiniPin routine [Streaming Media Devices], PFNKSPINVOID, avstclbk_7d4db969-3c67-4f42-9b06-723964af1147.xml, ks/MyAVStrMiniPin, stream.avstrminipindisconnect
f1_keywords:
 - "ks/MyAVStrMiniPin"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- MyAVStrMiniPin
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSPINVOID callback function


## -description


An AVStream minidriver's callback routine is called when:
<ul>
<li>The relevant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> is serving as a sink pin and this sink pin is disconnected from an AVStream source pin.</li>
<li>A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure's reset state is changed due to the arrival of an IOCTL_KS_RESET_STATE device control. This routine is also called when the queue associated with the given pin is flushed. </li>
</ul>

## -parameters




### -param Pin [in]

Pointer to the relevant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>, serving as a sink pin.


## -remarks



<b>About AVStrMiniPinDisconnect</b>

The minidriver specifies this routine's address in the <b>Disconnect</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure.

This routine is optional.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-pins">KS Pins</a>.

<b>About AVStrMiniPinReset</b>

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a>.

The minidriver specifies this routine's address in the <b>Reset</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure.

Typically, this routine is provided by minidrivers that must flush hardware buffers. The filter control mutex may be held during this function. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-control-mutex-in-avstream">Filter Control Mutex in AVStream</a>.

This routine is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>
 

 

