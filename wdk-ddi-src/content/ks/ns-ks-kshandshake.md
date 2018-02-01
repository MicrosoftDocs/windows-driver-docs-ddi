---
UID: NS:ks.KSHANDSHAKE
title: KSHANDSHAKE
author: windows-driver-content
description: The KSHANDSHAKE structure is used to pass information back and forth while pins are handshaking in an attempt to negotiate a private interface.
old-location: stream\kshandshake.htm
old-project: stream
ms.assetid: fe163d23-0eaf-4a3e-b371-2f65f2235251
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSHANDSHAKE structure [Streaming Media Devices], KSHANDSHAKE, *PKSHANDSHAKE, ks/KSHANDSHAKE, stream.kshandshake, avstruct_65ba3a40-5560-4acb-bf85-90fa9ad46fc1.xml, PKSHANDSHAKE, PKSHANDSHAKE structure pointer [Streaming Media Devices], ks/PKSHANDSHAKE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSHANDSHAKE
product: Windows
targetos: Windows
req.typenames: "*PKSHANDSHAKE, KSHANDSHAKE"
---

# KSHANDSHAKE structure


## -description


The KSHANDSHAKE structure is used to pass information back and forth while pins are handshaking in an attempt to negotiate a private interface.


## -syntax


````
typedef struct {
  GUID  ProtocolId;
  PVOID Argument1;
  PVOID Argument2;
} KSHANDSHAKE, *PKSHANDSHAKE;
````


## -struct-fields




### -field ProtocolId

This member specifies the GUID that represents the interface or protocol being negotiated between two AVStream pins.


### -field Argument1

A pointer to an interface-dependent argument. Most often, this is used to pass back and forth COM-style interface pointers once a specific private interface or protocol has been agreed upon. 


### -field Argument2

A pointer to an interface-dependent argument.


## -remarks


See <a href="..\ks\nf-ks-kspinhandshake.md">KsPinHandshake</a> for more information about negotiating private interfaces between AVStream pins.

Pin handshaking is a concept that is usable only between two pins that support IOCTL_KS_HANDSHAKE. Currently, only AVStream pins support this interface; thus this is only useful for negotiating private interfaces between two AVStream pins. Currently, connections between AVStream pins are negotiated via this mechanism.



## -see-also

<a href="..\ks\nf-ks-kspinhandshake.md">KsPinHandshake</a>

<a href="..\ks\ni-ks-ioctl_ks_handshake.md">IOCTL_KS_HANDSHAKE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSHANDSHAKE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

