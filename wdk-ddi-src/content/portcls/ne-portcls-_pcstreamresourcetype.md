---
UID: NE:portcls._PcStreamResourceType
title: "_PcStreamResourceType"
description: This topic discusses the PcStreamResourceType enum, and describes its members. The PcStreamResourceType enum is used to define the type of resources used for specific audio streaming.
old-location: audio\pcstreamresourcetype.htm
tech.root: audio
ms.assetid: C9563635-66F3-4835-8153-DECB04580544
ms.date: 05/08/2018
ms.keywords: "*PPcStreamResourceType, PcStreamResourceType, PcStreamResourceType enumeration [Audio Devices], PcStreamResourceType,*PPcStreamResourceType, PcStreamResourceType,*PPcStreamResourceType enumeration [Audio Devices], _PcStreamResourceType, audio.pcstreamresourcetype, ePcStreamResourceInterrupt, ePcStreamResourceSet, ePcStreamResourceThread, portcls/PcStreamResourceType, portcls/ePcStreamResourceInterrupt, portcls/ePcStreamResourceSet, portcls/ePcStreamResourceThread"
ms.topic: enum
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	Portcls.h
api_name:
-	PcStreamResourceType, *PPcStreamResourceType
product:
- Windows
targetos: Windows
req.typenames: PcStreamResourceType, *PPcStreamResourceType
---

# _PcStreamResourceType enumeration


## -description


This topic discusses the PcStreamResourceType enum, and describes its members. The PcStreamResourceType enum is used to define the type of resources used for specific audio streaming 


## -enum-fields




### -field ePcStreamResourceInterrupt

The resource is a PKINTERRUPT. 


### -field ePcStreamResourceThread

 The resource is a PETHREAD. 


### -field ePcStreamResourceSet

The resource is a link to another device-stack’s resources. 


## -remarks



Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. Two type of stream resources are supported: interrupts and driver-owned threads. Audio drivers should register a resource after creating the resource, and unregister the resource before deleted it. 




