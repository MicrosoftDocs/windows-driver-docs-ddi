---
UID: NF:ks.KsPinRegisterHandshakeCallback
title: KsPinRegisterHandshakeCallback function
author: windows-driver-content
description: The KsPinRegisterHandshakeCallback function registers a minidriver-provided callback routine for a given pin.
old-location: stream\kspinregisterhandshakecallback.htm
old-project: stream
ms.assetid: a5b9f731-e029-40c2-9fbb-d7a3b63615df
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsPinRegisterHandshakeCallback, stream.kspinregisterhandshakecallback, avfunc_9588944b-a56b-473a-848d-0a01031b6911.xml, KsPinRegisterHandshakeCallback function [Streaming Media Devices], KsPinRegisterHandshakeCallback
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
-	KsPinRegisterHandshakeCallback
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterHandshakeCallback function


## -description


The<b> KsPinRegisterHandshakeCallback</b> function registers a minidriver-provided callback routine for a given pin. AVStream calls the callback routine when it receives a handshake request for the pin that specifies a protocol that AVStream does not handle by default. 


## -syntax


````
void KsPinRegisterHandshakeCallback(
  _In_ PKSPIN            Pin,
  _In_ PFNKSPINHANDSHAKE Handshake
);
````


## -parameters




### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to register a handshake callback.


### -param Handshake [in]

A pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkspinhandshake.md">AVStrMiniPinHandshake</a> routine to be called when AVStream receives a protocol handshake request on <i>Pin</i> that it does not handle.


## -returns



None




## -remarks



Pins that support private protocol connections with other AVStream pins should register a handshake callback.

Minidrivers that support private protocols between a given pin and another AVStream pin should call this routine as soon as possible to register a callback. Then if another pin requests a handshake, the minidriver can return the request. 




## -see-also

<a href="..\ks\nf-ks-ksfilterregisterpowercallbacks.md">KsFilterRegisterPowerCallbacks</a>



<a href="..\ks\nf-ks-kspinregisterpowercallbacks.md">KsPinRegisterPowerCallbacks</a>



<a href="..\ks\nc-ks-pfnkspinhandshake.md">AVStrMiniPinHandshake</a>



<a href="..\ks\nf-ks-kspinhandshake.md">KsPinHandshake</a>



<a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a>



<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinRegisterHandshakeCallback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

