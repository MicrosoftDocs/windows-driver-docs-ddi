---
UID: NS:ks.__unnamed_struct_83
title: KSHANDSHAKE (ks.h)
description: The KSHANDSHAKE structure is used to pass information back and forth while pins are handshaking in an attempt to negotiate a private interface.
old-location: stream\kshandshake.htm
tech.root: stream
ms.assetid: fe163d23-0eaf-4a3e-b371-2f65f2235251
ms.date: 04/23/2018
keywords: ["KSHANDSHAKE structure"]
ms.keywords: "*PKSHANDSHAKE, KSHANDSHAKE, KSHANDSHAKE structure [Streaming Media Devices], PKSHANDSHAKE, PKSHANDSHAKE structure pointer [Streaming Media Devices], avstruct_65ba3a40-5560-4acb-bf85-90fa9ad46fc1.xml, ks/KSHANDSHAKE, ks/PKSHANDSHAKE, stream.kshandshake"
f1_keywords:
 - "ks/KSHANDSHAKE"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
- HeaderDef
api_location:
- ks.h
api_name:
- KSHANDSHAKE
product:
- Windows
targetos: Windows
req.typenames: KSHANDSHAKE, *PKSHANDSHAKE
---

# KSHANDSHAKE structure


## -description


The KSHANDSHAKE structure is used to pass information back and forth while pins are handshaking in an attempt to negotiate a private interface.


## -struct-fields




### -field ProtocolId

This member specifies the GUID that represents the interface or protocol being negotiated between two AVStream pins.


### -field Argument1

A pointer to an interface-dependent argument. Most often, this is used to pass back and forth COM-style interface pointers once a specific private interface or protocol has been agreed upon. 


### -field Argument2

A pointer to an interface-dependent argument.


## -remarks



See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinhandshake">KsPinHandshake</a> for more information about negotiating private interfaces between AVStream pins.

Pin handshaking is a concept that is usable only between two pins that support IOCTL_KS_HANDSHAKE. Currently, only AVStream pins support this interface; thus this is only useful for negotiating private interfaces between two AVStream pins. Currently, connections between AVStream pins are negotiated via this mechanism.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ni-ks-ioctl_ks_handshake">IOCTL_KS_HANDSHAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinhandshake">KsPinHandshake</a>
 

 

