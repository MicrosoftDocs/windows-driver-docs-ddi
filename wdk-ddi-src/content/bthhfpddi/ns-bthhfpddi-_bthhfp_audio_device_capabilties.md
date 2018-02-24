---
UID: NS:bthhfpddi._BTHHFP_AUDIO_DEVICE_CAPABILTIES
title: "_BTHHFP_AUDIO_DEVICE_CAPABILTIES"
author: windows-driver-content
description: The BTHHFP_AUDIO_DEVICE_CAPABILTIES data structure describes the capabilities of a Bluetooth HFP device, including the version and whether it supports 16 kHz sampling.
old-location: audio\bthhfp_audio_device_capabilties.htm
old-project: audio
ms.assetid: 56c2bbb9-8fcd-43d4-9202-c8925575e44d
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: BTHHFP_AUDIO_DEVICE_CAPABILTIES, *PBTHHFP_AUDIO_DEVICE_CAPABILTIES, _BTHHFP_AUDIO_DEVICE_CAPABILTIES, bthhfpddi/BTHHFP_AUDIO_DEVICE_CAPABILTIES, BTHHFP_AUDIO_DEVICE_CAPABILTIES structure [Audio Devices], audio.bthhfp_audio_device_capabilties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthhfpddi.h
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
-	bthhfpddi.h
apiname:
-	BTHHFP_AUDIO_DEVICE_CAPABILTIES
product: Windows
targetos: Windows
req.typenames: BTHHFP_AUDIO_DEVICE_CAPABILTIES, *PBTHHFP_AUDIO_DEVICE_CAPABILTIES
---

# _BTHHFP_AUDIO_DEVICE_CAPABILTIES structure


## -description


The <b>BTHHFP_AUDIO_DEVICE_CAPABILTIES</b> data structure describes the capabilities of a Bluetooth HFP device, including the version and whether it supports 16 kHz sampling.


## -syntax


````
typedef struct _BTHHFP_AUDIO_DEVICE_CAPABILTIES {
  DWORD Version;
  BOOL  Supports16kHzSampling;
} BTHHFP_AUDIO_DEVICE_CAPABILTIES, BTHHFP_AUDIO_DEVICE_CAPABILTIES;
````


## -struct-fields




### -field Version

The version of the device.


### -field Supports16kHzSampling

Whether the device supports 16 kHz sampling.

