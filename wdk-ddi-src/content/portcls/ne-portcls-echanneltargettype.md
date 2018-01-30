---
UID: NE:portcls.eChannelTargetType
title: eChannelTargetType
author: windows-driver-content
description: The eChannelTargetType enumeration defines constants that specify a type of node (target) in a given channel.
old-location: audio\echanneltargettype.htm
old-project: audio
ms.assetid: 44C5BE49-E8D5-4E6C-BDC5-494F180D580A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.echanneltargettype, eVolumeAttribute, portcls/eVolumeAttribute, eChannelTargetType, eMuteAttribute, ePeakMeterAttribute, portcls/ePeakMeterAttribute, eChannelTargetType enumeration [Audio Devices], portcls/eChannelTargetType, portcls/eMuteAttribute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	eChannelTargetType
product: Windows
targetos: Windows
req.typenames: eChannelTargetType
---

# eChannelTargetType enumeration


## -description


The <b>eChannelTargetType</b> enumeration defines constants that specify a type of node (target) in a given channel.


## -syntax


````
typedef enum _eChannelTargetType { 
  eVolumeAttribute,
  eMuteAttribute,
  ePeakMeterAttribute
} eChannelTargetType;
````


## -enum-fields




### -field eVolumeAttribute

Indicates a volume level control node.


### -field eMuteAttribute

Indicates a Mute node.


### -field ePeakMeterAttribute

Indicates a PeakMeter node.

