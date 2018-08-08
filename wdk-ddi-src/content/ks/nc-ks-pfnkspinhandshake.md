---
UID: NC:ks.PFNKSPINHANDSHAKE
title: PFNKSPINHANDSHAKE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinHandshake routine is called when AVStream receives a protocol handshake request that it does not handle.
old-location: stream\avstrminipinhandshake.htm
tech.root: stream
ms.assetid: cebeceb1-f845-42cf-9a8b-3414e4a420b6
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: AVStrMiniPinHandshake, AVStrMiniPinHandshake routine [Streaming Media Devices], PFNKSPINHANDSHAKE, avstclbk_3a87dcb0-5825-4ba0-b9b3-dfb6a1af20a2.xml, ks/AVStrMiniPinHandshake, stream.avstrminipinhandshake
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniPinHandshake
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSPINHANDSHAKE callback function


## -description


An AVStream minidriver's <i>AVStrMiniPinHandshake</i> routine is called when AVStream receives a protocol handshake request that it does not handle.


## -parameters




### -param Pin


### -param In


### -param Out








#### - Data [in]

Pointer to a caller-allocated buffer. If the pin supports the requested protocol, <i>AVStrMiniPinHandshake</i> should fill in this parameter with a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562673">KSHANDSHAKE</a> structure.


#### - Irp [in]

Pointer to the IRP containing the handshake request.


#### - Request [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562676">KSIDENTIFIER</a> structure that contains a GUID identifying the requested protocol.


## -returns



Returns STATUS_SUCCESS if the pin supports the requested protocol. Otherwise, it should return STATUS_INVALID_DEVICE_REQUEST.




## -remarks



The minidriver specifies this routine's address in the <i>Handshake</i> parameter of a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563523">KsPinRegisterHandshakeCallback</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562673">KSHANDSHAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562676">KSIDENTIFIER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563523">KsPinRegisterHandshakeCallback</a>
 

 

