---
UID: NS:d3dkmdt._D3DKMDT_WIRE_FORMAT_AND_PREFERENCE
title: "_D3DKMDT_WIRE_FORMAT_AND_PREFERENCE"
author: windows-driver-content
description: Holds information about the preferred pixel encoding format.
old-location: display\d3dkmdt_wire_format_and_preference.htm
old-project: display
ms.assetid: 24CC6A10-6462-4681-B340-E887B679F456
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmdt_wire_format_and_preference, D3DKMDT_WIRE_FORMAT_AND_PREFERENCE union [Display Devices], PD3DKMDT_WIRE_FORMAT_AND_PREFERENCE, *PD3DKMDT_WIRE_FORMAT_AND_PREFERENCE, D3DKMDT_WIRE_FORMAT_AND_PREFERENCE, _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE, d3dkmdt/PD3DKMDT_WIRE_FORMAT_AND_PREFERENCE, PD3DKMDT_WIRE_FORMAT_AND_PREFERENCE union pointer [Display Devices], d3dkmdt/D3DKMDT_WIRE_FORMAT_AND_PREFERENCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
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
-	d3dkmdt.h
apiname:
-	D3DKMDT_WIRE_FORMAT_AND_PREFERENCE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_WIRE_FORMAT_AND_PREFERENCE, *PD3DKMDT_WIRE_FORMAT_AND_PREFERENCE
---

# _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE structure


## -description


Holds information about the preferred pixel encoding format.


## -syntax


````
typedef union _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE {
  struct {
    D3DKMDT_MODE_PREFERENCE Preference  :2;
    UINT                    Rgb  :6;
    UINT                    YCbCr444  :6;
    UINT                    YCbCr422  :6;
    UINT                    YCbCr420  :6;
    UINT                    Intensity  :6;
  };
  UINT Value;
} D3DKMDT_WIRE_FORMAT_AND_PREFERENCE, *PD3DKMDT_WIRE_FORMAT_AND_PREFERENCE;
````


## -struct-fields




### -field Preference

Functions as it has in previous releases, but using only 2 bits.


### -field Rgb

UINT describing supported/requested pixel encoding using RGB sample format.


### -field YCbCr444

UINT describing supported/requested pixel encoding using YcbCr 4:4:4 sample format.


### -field YCbCr422

UINT describing supported/requested pixel encoding using YcbCr 4:2:2 sample format.


### -field YCbCr420

UINT describing supported/requested pixel encoding using YcbCr 4:2:0 sample format.


### -field Intensity

UINT describing supported/requested pixel encoding using intensity only.


### -field Value

UINT used to operate on the combined bit-fields.


## -remarks



The five standard color sample formats for pixel transmission are exposed separately to allow the driver to report capabilities individually but it is expected that the vast majority of display devices will not support all sample formats as input, in particular support of intensity only signals is likely restricted to monochrome displays which should therefore not support color sample formats.

During mode enumeration via EnumVidPnCofuncModality, the driver should set values into all five fields to indicate the pixel encodings that are supported as inputs to the display device in the current configuration.

When SetTimingsFromVidPn is called, one of these fields will indicate the pixel encoding and sample format to be applied.




