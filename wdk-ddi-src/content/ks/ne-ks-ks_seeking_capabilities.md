---
UID: NE:ks.KS_SEEKING_CAPABILITIES
title: KS_SEEKING_CAPABILITIES
author: windows-driver-content
description: "."
old-location: stream\ks_seeking_capabilities.htm
old-project: stream
ms.assetid: 345ADD1F-2002-4F9C-942C-212CADCF84E5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ks/KS_SEEKING_CanSeekAbsolute, KS_SEEKING_CanSeekForwards, ks/KS_SEEKING_CanGetStopPos, ks/KS_SEEKING_CanSeekBackwards, KS_SEEKING_CanSeekBackwards, KS_SEEKING_CanSeekAbsolute, KS_SEEKING_CAPABILITIES enumeration [Streaming Media Devices], ks/KS_SEEKING_CAPABILITIES, ks/KS_SEEKING_CanSeekForwards, KS_SEEKING_CAPABILITIES, KS_SEEKING_CanGetDuration, ks/KS_SEEKING_CanGetDuration, KS_SEEKING_CanPlayBackwards, stream.ks_seeking_capabilities, KS_SEEKING_CanGetStopPos, ks/KS_SEEKING_CanPlayBackwards, KS_SEEKING_CanGetCurrentPos, ks/KS_SEEKING_CanGetCurrentPos
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	KS_SEEKING_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: KS_SEEKING_CAPABILITIES
---

# KS_SEEKING_CAPABILITIES enumeration


## -description





## -syntax


````
typedef enum  { 
  KS_SEEKING_CanSeekAbsolute   = 0x1,
  KS_SEEKING_CanSeekForwards   = 0x2,
  KS_SEEKING_CanSeekBackwards  = 0x4,
  KS_SEEKING_CanGetCurrentPos  = 0x8,
  KS_SEEKING_CanGetStopPos     = 0x10,
  KS_SEEKING_CanGetDuration    = 0x20,
  KS_SEEKING_CanPlayBackwards  = 0x40
} KS_SEEKING_CAPABILITIES;
````


## -enum-fields




### -field KS_SEEKING_CanSeekAbsolute


### -field KS_SEEKING_CanSeekForwards


### -field KS_SEEKING_CanSeekBackwards


### -field KS_SEEKING_CanGetCurrentPos


### -field KS_SEEKING_CanGetStopPos


### -field KS_SEEKING_CanGetDuration


### -field KS_SEEKING_CanPlayBackwards

