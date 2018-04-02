---
UID: NF:ks.KsPinHandshake
title: KsPinHandshake function
author: windows-driver-content
description: The KsPinHandshake function attempts a protocol handshake with a connected pin.
old-location: stream\kspinhandshake.htm
old-project: stream
ms.assetid: 31855688-9221-4128-89c5-dbc4f3e6f794
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinHandshake, KsPinHandshake function [Streaming Media Devices], avfunc_a7b6afa8-acb0-4847-9e86-136100c4dd48.xml, ks/KsPinHandshake, stream.kspinhandshake
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsPinHandshake
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinHandshake function


## -description


The<b> KsPinHandshake </b>function attempts a protocol handshake with a connected pin.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure that is initiating the handshake. The handshake request is passed on to the pin connected to this object.


### -param In [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562673">KSHANDSHAKE</a> structure containing the handshake information to be passed to the connected pin.


### -param Out [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562673">KSHANDSHAKE</a> structure that is filled in with handshake information by the connected pin.


## -returns



<b>KsPinHandshake </b>returns STATUS_SUCCESS if the connected pin is accepting the negotiated connection. Otherwise, it returns an appropriate error code.




## -remarks



Protocol handshakes can be used to negotiate private interfaces between two pins that are both AVStream pins. 

Connections between AVStream pins are performed using this type of handshake.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560813">IOCTL_KS_HANDSHAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562673">KSHANDSHAKE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563509">KsPinGetConnectedPinInterface</a>
 

 

