---
UID: NF:portcls.IPortWavePciStream.TerminatePacket
title: IPortWavePciStream::TerminatePacket (portcls.h)
description: The TerminatePacket method terminates the packet currently being mapped.
old-location: audio\iportwavepcistream_terminatepacket.htm
tech.root: audio
ms.assetid: b85c37ff-b8f0-43df-bce2-f8a85ec050a7
ms.date: 05/08/2018
ms.keywords: IPortWavePciStream interface [Audio Devices],TerminatePacket method, IPortWavePciStream.TerminatePacket, IPortWavePciStream::TerminatePacket, TerminatePacket, TerminatePacket method [Audio Devices], TerminatePacket method [Audio Devices],IPortWavePciStream interface, audio.iportwavepcistream_terminatepacket, audmp-routines_7991fb3b-ea9a-4c58-acd5-7563752f415e.xml, portcls/IPortWavePciStream::TerminatePacket
f1_keywords:
 - "portcls/IPortWavePciStream.TerminatePacket"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IPortWavePciStream.TerminatePacket
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWavePciStream::TerminatePacket


## -description


The <code>TerminatePacket</code> method terminates the packet currently being mapped.


## -returns



<code>TerminatePacket</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



This method is used primarily for capture situations in which I/O packets need to end at specific points in the stream (for example, to synchronize with video frames). The data buffer for a capture pin on an audio device consists of one or more I/O packets. Each I/O packet is the portion of the data buffer that is attached to a particular mapping IRP. By default, while a capture stream is in the KSSTATE_RUN state, the contents of an I/O packet become available to the client only when the last mapping in the packet has been filled. The <code>TerminatePacket</code> method makes a partially filled packet immediately available to the client without waiting for additional capture data.

Changing the state of a capture stream from KSSTATE_RUN to KSSTATE_STOP automatically terminates the current I/O packet.



