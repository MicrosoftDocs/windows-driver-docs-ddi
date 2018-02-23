---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES
title: "_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES"
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_ep_shadow_resources.htm
old-project: audio
ms.assetid: 56159F97-82CD-4F0A-ADF0-228E876A0266
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: usbsidebandaudio/USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, audio.usbsidebandaudio_ep_shadow_resources, PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES structure pointer [Audio Devices], *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, usbsidebandaudio/PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES structure [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbsidebandaudio.h
req.include-header: Usbsidebandaudio.h
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
-	kbSyntax
apitype:
-	<TBD>
apilocation:
-
apiname:
-	USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES
product: Windows
targetos: Windows
req.typenames: USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD


## -syntax


````
typedef struct _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES {
  ULONG                                          Reserved 0;
  ULONG                                          Reserved 1;
  PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION Reserved 2;
  LONGLONG                                       Reserved 3;
} USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES, *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES;
````


## -struct-fields




### -field CbSize

 


### -field CbDataSize

 


### -field pEpFunctionResources

 


### -field ShadowResourceBlob

 




#### - Reserved 0

TBD


#### - Reserved 1

TBD


#### - Reserved 2

TBD


#### - Reserved 3

TBD

