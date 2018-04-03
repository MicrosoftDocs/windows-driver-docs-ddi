---
UID: NS:msviddrv.tag_video_open_parms
title: tag_video_open_parms
author: windows-driver-content
description: "."
old-location: stream\video_open_parms.htm
old-project: stream
ms.assetid: BD11B67F-9229-4584-A20D-7D7C70B42977
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*LPVIDEO_OPEN_PARMS, LPVIDEO_OPEN_PARMS, LPVIDEO_OPEN_PARMS structure pointer [Streaming Media Devices], VIDEO_OPEN_PARMS, VIDEO_OPEN_PARMS structure [Streaming Media Devices], msviddrv/LPVIDEO_OPEN_PARMS, msviddrv/VIDEO_OPEN_PARMS, stream.video_open_parms, tag_video_open_parms"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: msviddrv.h
req.include-header: 
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Msviddrv.h
api_name:
-	VIDEO_OPEN_PARMS
product:
- Windows
targetos: Windows
req.typenames: VIDEO_OPEN_PARMS, *LPVIDEO_OPEN_PARMS
---

# tag_video_open_parms structure


## -description





## -struct-fields




### -field dwSize

Set to the size of the <b>VIDEO_OPEN_PARMS</b> structure.


### -field fccType

'vcap'


### -field fccComp

This member is not used.


### -field dwVersion

Specifies the version of msvideo.


### -field dwFlags

Specifies the type of channel.


### -field dwError

If open fails, specifies why it failed.


### -field pV1Reserved

Reserved.


### -field pV2Reserved

Reserved.


### -field dnDevNode

Specifies the devnode for PnP devices.

