---
UID: NS:d3dkmdt._DXGK_MONITORLINKINFO_CAPABILITIES
title: _DXGK_MONITORLINKINFO_CAPABILITIES
author: windows-driver-content
description: Flags which describe the capabilities for driving the monitor.
old-location: display\dxgk_monitorlinkinfo_capabilities.htm
old-project: display
ms.assetid: 9838DF74-6561-40DB-A745-A15005B97AAC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_MONITORLINKINFO_CAPABILITIES, DXGK_MONITORLINKINFO_CAPABILITIES, *PDXGK_MONITORLINKINFO_CAPABILITIES
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
req.alt-api: DXGK_MONITORLINKINFO_CAPABILITIES
req.alt-loc: d3dkmdt.h
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
req.typenames: DXGK_MONITORLINKINFO_CAPABILITIES, *PDXGK_MONITORLINKINFO_CAPABILITIES
---

# _DXGK_MONITORLINKINFO_CAPABILITIES structure



## -description
Flags which describe the capabilities for driving the monitor.



## -syntax

````
typedef union _DXGK_MONITORLINKINFO_CAPABILITIES {
  struct {
    UINT Stereo  :1;
    UINT WideColorSpace  :1;
    UINT HighColorSpace  :1;
    UINT DynamicColorSpace  :1;
    UINT DynamicBitsPerColorChannel  :1;
    UINT DynamicColorEncodingFormat  :1;
    UINT DedicatedTimingGeneration  :1;
  };
  UINT Reserved  :25;
} DXGK_MONITORLINKINFO_CAPABILITIES, *PDXGK_MONITORLINKINFO_CAPABILITIES;
````


## -struct-fields

### -field Stereo

If TRUE and resources are not constrained by other paths, stereo display modes are supported.


### -field WideColorSpace

If TRUE, the driver has the hardware capability to perform 3x3 rotation matrix to transform RGB values from the gamut defined by the sRGB/709 primaries to the panel’s primaries. The driver can also send any necessary control signaling to the connected display to indicate the correct interpretation of the pixel data being sent. This includes handling signed input in the range (-2.0 to 2.0). The driver must do this with all input surface formats 8888, 10-10-102, and fp16.


### -field HighColorSpace

If TRUE, the driver supports all of the above WideColorSpace gamut functionality and also has the ability to apply the appropriate transfer curve for that display. This means accepting canonical color space data in the range [-128.0 to 256.0] and sending any necessary control signaling to the connected display to indicate the correct interpretation.


### -field DynamicColorSpace

If TRUE, the display miniport driver supports seamless changing of the color space on this display if no other attributes are changed which would cause a glitch. If FALSE, seamless changing of color space is not supported. 


### -field DynamicBitsPerColorChannel

If TRUE, the display miniport driver supports seamless changing of the wire format bits per color channel on this display if no other attributes are changed which would cause a glitch. If FALSE, seamless changing of bits per color channel is not supported. 


### -field DynamicColorEncodingFormat

If TRUE, the display miniport driver supports seamless changing of the wire format color encoding on this display if no other attributes are changed which would cause a glitch. If FALSE, seamless changing of color encoding is not supported. 


### -field DedicatedTimingGeneration

If TRUE, the timing generation for this display is independent from the timing generation of other displays such that mode enumeration for this target may be performed in isolation from other active targets. Changing timing on this display does not change the timings available for any other display and vice versa.

In general, this flag is target based rather than based on the combination of the target and the attached display. However, there may be cases where some baseline capability is dedicated but beyond the baseline resources that are shared across targets.  In this case, if the attached display’s maximum requirements fit within the baseline, the driver would be able to report the timing generation as dedicated and therefore enable optimized enumeration of cofunctional timings.


### -field Reserved

This value is reserved for system use.


## -remarks
