---
UID: NF:ks.KsPinRegisterHandshakeCallback
title: KsPinRegisterHandshakeCallback function (ks.h)
description: The KsPinRegisterHandshakeCallback function registers a minidriver-provided callback routine for a given pin.
old-location: stream\kspinregisterhandshakecallback.htm
tech.root: stream
ms.assetid: a5b9f731-e029-40c2-9fbb-d7a3b63615df
ms.date: 04/23/2018
ms.keywords: KsPinRegisterHandshakeCallback, KsPinRegisterHandshakeCallback function [Streaming Media Devices], avfunc_9588944b-a56b-473a-848d-0a01031b6911.xml, ks/KsPinRegisterHandshakeCallback, stream.kspinregisterhandshakecallback
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinRegisterHandshakeCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterHandshakeCallback function


## -description


The<b> KsPinRegisterHandshakeCallback</b> function registers a minidriver-provided callback routine for a given pin. AVStream calls the callback routine when it receives a handshake request for the pin that specifies a protocol that AVStream does not handle by default. 


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> structure for which to register a handshake callback.


### -param Handshake [in]

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspinhandshake">AVStrMiniPinHandshake</a> routine to be called when AVStream receives a protocol handshake request on <i>Pin</i> that it does not handle.


## -returns



None




## -remarks



Pins that support private protocol connections with other AVStream pins should register a handshake callback.

Minidrivers that support private protocols between a given pin and another AVStream pin should call this routine as soon as possible to register a callback. Then if another pin requests a handshake, the minidriver can return the request. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspinhandshake">AVStrMiniPinHandshake</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kshandshake">KSHANDSHAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfilterregisterpowercallbacks">KsFilterRegisterPowerCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinhandshake">KsPinHandshake</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinregisterpowercallbacks">KsPinRegisterPowerCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>
 

 

