---
UID: NE:bthhfpddi._HFP_BYPASS_CODEC_ID_VERSION
title: "_HFP_BYPASS_CODEC_ID_VERSION"
author: windows-driver-content
description: The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service.
old-location: audio\hfp_bypass_codec_id_version.htm
old-project: audio
ms.assetid: A16980CD-3F2F-4A67-902A-F3D72AA042D9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PHFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION enumeration [Audio Devices], REQ_HFP_BYPASS_CODEC_ID_V1, _HFP_BYPASS_CODEC_ID_VERSION, audio.hfp_bypass_codec_id_version, bthhfpddi/HFP_BYPASS_CODEC_ID_VERSION, bthhfpddi/REQ_HFP_BYPASS_CODEC_ID_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthhfpddi.h
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthhfpddi.h
api_name:
-	HFP_BYPASS_CODEC_ID_VERSION
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# _HFP_BYPASS_CODEC_ID_VERSION enumeration


## -description


The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service.


## -syntax


````
typedef enum _HFP_BYPASS_CODEC_ID_VERSION { 
  REQ_HFP_BYPASS_CODEC_ID_V1  = 1
} HFP_BYPASS_CODEC_ID_VERSION;
````


## -enum-fields




### -field REQ_HFP_BYPASS_CODEC_ID_V1

Codec ID structure version 1.


## -see-also

<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_codec_id.md">IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</a>



<a href="..\bthhfpddi\ns-bthhfpddi-_hfp_bypass_codec_id_v1.md">HFP_BYPASS_CODEC_ID_V1</a>



 

 


