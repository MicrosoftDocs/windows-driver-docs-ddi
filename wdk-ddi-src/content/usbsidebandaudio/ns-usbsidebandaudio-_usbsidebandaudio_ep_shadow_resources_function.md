---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION
title: "_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION"
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_ep_shadow_resources_function.htm
old-project: audio
ms.assetid: 554C5829-D9C0-4F5F-B88A-285A31415CD3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure pointer [Audio Devices], USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure [Audio Devices], _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, audio.usbsidebandaudio_ep_shadow_resources_function, usbsidebandaudio/PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, usbsidebandaudio/USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION"
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
-	USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION
product: Windows
targetos: Windows
req.typenames: USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD


## -syntax


````
typedef struct _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION {
  ULONG                    Reserved 0;
  PUSB_ENDPOINT_DESCRIPTOR Reserved 1;
  USHORT                   Reserved 2;
  UCHAR                    Reserved 3;
  UCHAR                    Reserved 4;
} USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION;
````


## -struct-fields




### -field CbSize

 


### -field pUsbEndpointDescriptor

 


### -field bcdAudioSpec

 


### -field bDelay

 


### -field bSlotSize

 




#### - Reserved 0

TBD


#### - Reserved 1

TBD


#### - Reserved 2

TBD


#### - Reserved 3

TBD


#### - Reserved 4

TBD

