---
UID: NE:portcls._PcStreamResourceType
title: "_PcStreamResourceType"
author: windows-driver-content
description: This topic discusses the PcStreamResourceType enum, and describes its members. The PcStreamResourceType enum is used to define the type of resources used for specific audio streaming.
old-location: audio\pcstreamresourcetype.htm
old-project: audio
ms.assetid: C9563635-66F3-4835-8153-DECB04580544
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "*PPcStreamResourceType, PcStreamResourceType enumeration [Audio Devices], PcStreamResourceType, *PPcStreamResourceType enumeration [Audio Devices], ePcStreamResourceThread, portcls/PcStreamResourceType, ePcStreamResourceInterrupt, portcls/ePcStreamResourceThread, PcStreamResourceType, portcls/ePcStreamResourceSet, portcls/ePcStreamResourceInterrupt, PcStreamResourceType, *PPcStreamResourceType, _PcStreamResourceType, ePcStreamResourceSet, audio.pcstreamresourcetype"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Portcls.h
apiname:
-	PcStreamResourceType, *PPcStreamResourceType
product: Windows
targetos: Windows
req.typenames: PcStreamResourceType, *PPcStreamResourceType
---

# _PcStreamResourceType enumeration


## -description


This topic discusses the PcStreamResourceType enum, and describes its members. The PcStreamResourceType enum is used to define the type of resources used for specific audio streaming 


## -syntax


````
typedef enum PcStreamResourceType { 
  ePcStreamResourceInterrupt,
  ePcStreamResourceThread,
  ePcStreamResourceSet
} PcStreamResourceType, *PPcStreamResourceType;
````


## -enum-fields




### -field ePcStreamResourceInterrupt

The resource is a PKINTERRUPT. 


### -field ePcStreamResourceThread

 The resource is a PETHREAD. 


### -field ePcStreamResourceSet

The resource is a link to another device-stack’s resources. 


## -remarks



Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. Two type of stream resources are supported: interrupts and driver-owned threads. Audio drivers should register a resource after creating the resource, and unregister the resource before deleted it. 




