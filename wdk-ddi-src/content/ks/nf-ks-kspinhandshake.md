---
UID: NF:ks.KsPinHandshake
title: KsPinHandshake function (ks.h)
description: The KsPinHandshake function attempts a protocol handshake with a connected pin.
old-location: stream\kspinhandshake.htm
tech.root: stream
ms.assetid: 31855688-9221-4128-89c5-dbc4f3e6f794
ms.date: 04/23/2018
keywords: ["KsPinHandshake function"]
ms.keywords: KsPinHandshake, KsPinHandshake function [Streaming Media Devices], avfunc_a7b6afa8-acb0-4847-9e86-136100c4dd48.xml, ks/KsPinHandshake, stream.kspinhandshake
f1_keywords:
 - "ks/KsPinHandshake"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsPinHandshake
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinHandshake function


## -description


The<b> KsPinHandshake </b>function attempts a protocol handshake with a connected pin.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure that is initiating the handshake. The handshake request is passed on to the pin connected to this object.


### -param In [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kshandshake">KSHANDSHAKE</a> structure containing the handshake information to be passed to the connected pin.


### -param Out [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kshandshake">KSHANDSHAKE</a> structure that is filled in with handshake information by the connected pin.


## -returns



<b>KsPinHandshake </b>returns STATUS_SUCCESS if the connected pin is accepting the negotiated connection. Otherwise, it returns an appropriate error code.




## -remarks



Protocol handshakes can be used to negotiate private interfaces between two pins that are both AVStream pins. 

Connections between AVStream pins are performed using this type of handshake.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ni-ks-ioctl_ks_handshake">IOCTL_KS_HANDSHAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kshandshake">KSHANDSHAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>
 

 

