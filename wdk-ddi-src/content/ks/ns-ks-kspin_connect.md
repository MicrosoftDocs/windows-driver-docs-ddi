---
UID: NS:ks.__unnamed_struct_33
title: KSPIN_CONNECT
author: windows-driver-content
description: Clients use the KSPIN_CONNECT structure to describe the connection they request from a driver in a KsCreatePin call.
old-location: stream\kspin_connect.htm
tech.root: stream
ms.assetid: 62ce7a36-87ce-40d1-bdd4-8a4f4bc60b00
ms.date: 04/23/2018
ms.keywords: "*PKSPIN_CONNECT, KSPIN_CONNECT, KSPIN_CONNECT structure [Streaming Media Devices], PKSPIN_CONNECT, PKSPIN_CONNECT structure pointer [Streaming Media Devices], ks-struct_07642f18-c766-4649-b97a-12582aa0fffb.xml, ks/KSPIN_CONNECT, ks/PKSPIN_CONNECT, stream.kspin_connect"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSPIN_CONNECT
product:
- Windows
targetos: Windows
req.typenames: KSPIN_CONNECT, *PKSPIN_CONNECT
---

# KSPIN_CONNECT structure


## -description


Clients use the KSPIN_CONNECT structure to describe the connection they request from a driver in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561652">KsCreatePin</a> call.


## -struct-fields




### -field Interface

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a> to use for this connection. 


### -field Medium

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> that specifies the medium to use for this connection. 


### -field PinId

Specifies the pin type ID number. If the PinToHandle field is not <b>NULL</b>, this field contains the identifier of the source pin to which the request is being sent. Otherwise this field refers to the sink pin that is being connected to. If a pin can support being both a source and sink in communications, then this is the implicit method of telling it how it should act in the connection.


### -field PinToHandle

Specifies what type of destination pin the create is intended for, and in the case of a source destination, what pin to connect to. This member is <b>NULL</b> when a client requests a connection to itself. Otherwise, it is the target of the connection request. In the case of a source destination, this contains the handle of the pin instance to establish a connection to. In the case of a sink destination, this field contains <b>NULL</b>, and is not otherwise used. 


### -field Priority

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564250">KSPRIORITY</a> that specifies the priority for the connection, usually KSPRIORITY_NORMAL. See the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565104">KSPROPERTY_CONNECTION_PRIORITY</a> property for details.


## -remarks



If the KSPIN_CONNECT.PinToHandle element is not <b>NULL</b>, IRP_MJ_CREATE instructs the device to connect the source KSPIN_CONNECT.PinId pin to the KSPIN_CONNECT.PinToHandle pin instance. Otherwise, this is a request from a client for connection to the KSPIN_CONNECT.PinId pin using the KSPIN_CONNECT.Medium method and a specific data format specified after the connection structure. In either case, the device driver may fail this request if this connection cannot be accepted.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565104">KSPROPERTY_CONNECTION_PRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561652">KsCreatePin</a>
 

 

