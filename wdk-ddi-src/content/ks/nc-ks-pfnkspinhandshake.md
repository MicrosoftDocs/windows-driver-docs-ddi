---
UID: NC:ks.PFNKSPINHANDSHAKE
title: PFNKSPINHANDSHAKE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinHandshake routine is called when AVStream receives a protocol handshake request that it does not handle.
old-location: stream\avstrminipinhandshake.htm
old-project: stream
ms.assetid: cebeceb1-f845-42cf-9a8b-3414e4a420b6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminipinhandshake, AVStrMiniPinHandshake, AVStrMiniPinHandshake routine [Streaming Media Devices], AVStrMiniPinHandshake, PFNKSPINHANDSHAKE, PFNKSPINHANDSHAKE, ks/AVStrMiniPinHandshake, avstclbk_3a87dcb0-5825-4ba0-b9b3-dfb6a1af20a2.xml
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
-	AVStrMiniPinHandshake
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSPINHANDSHAKE callback


## -description


An AVStream minidriver's <i>AVStrMiniPinHandshake</i> routine is called when AVStream receives a protocol handshake request that it does not handle.


## -prototype


````
PFNKSPINHANDSHAKE AVStrMiniPinHandshake;

NTSTATUS AVStrMiniPinHandshake(
  _In_ PKSPIN       Irp,
  _In_ PKSHANDSHAKE Request,
  _In_ PKSHANDSHAKE Data
)
{ ... }
````


## -parameters




### -param Pin



### -param In



### -param Out






#### - Irp [in]

Pointer to the IRP containing the handshake request.


#### - Request [in]

Pointer to a <a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a> structure that contains a GUID identifying the requested protocol.


#### - Data [in]

Pointer to a caller-allocated buffer. If the pin supports the requested protocol, <i>AVStrMiniPinHandshake</i> should fill in this parameter with a pointer to a <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> structure.


## -returns


Returns STATUS_SUCCESS if the pin supports the requested protocol. Otherwise, it should return STATUS_INVALID_DEVICE_REQUEST.



## -remarks


The minidriver specifies this routine's address in the <i>Handshake</i> parameter of a call to <a href="..\ks\nf-ks-kspinregisterhandshakecallback.md">KsPinRegisterHandshakeCallback</a>.



## -see-also

<a href="..\ks\nf-ks-kspinregisterhandshakecallback.md">KsPinRegisterHandshakeCallback</a>

<a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a>

<a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPINHANDSHAKE routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

