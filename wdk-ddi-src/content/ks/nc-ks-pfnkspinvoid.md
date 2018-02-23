---
UID: NC:ks.PFNKSPINVOID
title: PFNKSPINVOID
author: windows-driver-content
description: An AVStream minidriver's callback routine is called when:The relevant KSPIN is serving as a sink pin and this sink pin is disconnected from an AVStream source pin.A KSPIN structure's reset state is changed due to the arrival of an IOCTL_KS_RESET_STATE device control. This routine is also called when the queue associated with the given pin is flushed.
old-location: stream\avstrminipindisconnect.htm
old-project: stream
ms.assetid: 64bcbc05-8dbd-4f97-afbb-dadd44b60078
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.avstrminipindisconnect, AVStrMiniPinDisconnect, AVStrMiniPinReset, MyAVStrMiniPin routine [Streaming Media Devices], MyAVStrMiniPin, PFNKSPINVOID, PFNKSPINVOID, ks/MyAVStrMiniPin, avstclbk_7d4db969-3c67-4f42-9b06-723964af1147.xml
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
req.irql: 
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
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSPINVOID callback


## -description


An AVStream minidriver's callback routine is called when:
<ul>
<li>The relevant <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> is serving as a sink pin and this sink pin is disconnected from an AVStream source pin.</li>
<li>A <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure's reset state is changed due to the arrival of an IOCTL_KS_RESET_STATE device control. This routine is also called when the queue associated with the given pin is flushed. </li>
</ul>

## -prototype


````
PFNKSPINVOID MyAVStrMiniPin;

void MyAVStrMiniPin(
  _In_ PKSPIN Pin
)
{ ... }
````


## -parameters




### -param Pin [in]

Pointer to the relevant <a href="..\ks\ns-ks-_kspin.md">KSPIN</a>, serving as a sink pin.


## -returns



None




## -remarks



<b>About AVStrMiniPinDisconnect</b>

The minidriver specifies this routine's address in the <b>Disconnect</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

This routine is optional.

Also see <a href="https://msdn.microsoft.com/04d0d17b-c326-417d-b2e8-58b33420455a">KS Pins</a>.

<b>About AVStrMiniPinReset</b>

For more information, see <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>.

The minidriver specifies this routine's address in the <b>Reset</b> member of its <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a> structure.

Typically, this routine is provided by minidrivers that must flush hardware buffers. The filter control mutex may be held during this function. See <a href="https://msdn.microsoft.com/402795a0-e567-4e7e-a7d8-b2ce29ffb8fd">Filter Control Mutex in AVStream</a>.

This routine is optional.




## -see-also

<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINVOID routine%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

