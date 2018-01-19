---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
title: _USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_endpoint_descriptor.htm
old-project: audio
ms.assetid: 552986F7-AEE9-4CBF-A932-629885F99487
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, *PUSBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
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
req.alt-api: USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
req.alt-loc: 
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
req.typenames: *PUSBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD



## -syntax

````
typedef struct _USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR {
  ULONG                                   Reserved 0;
  GUID                                    Reserved 1;
  KSPIN_DATAFLOW                          Reserved 2;
   USBSIDEBANDAUDIO_ENDPOINT_CAPABILITIES Reserved 3;
  UNICODE_STRING                          Reserved 4;
  ULONG                                   Reserved 5;
  ULONG                                   Reserved 6;
} USBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR, *PUSBSIDEBANDAUDIO_ENDPOINT_DESCRIPTOR;
````


## -struct-fields

### -field Reserved 0

TBD


### -field Reserved 1

TBD


### -field Reserved 2

TBD


### -field Reserved 3

TBD


### -field Reserved 4

TBD


### -field Reserved 5

TBD


### -field Reserved 6

TBD


## -remarks
