---
UID: NE:d3dumddi._DXVADDI_NOMINALRANGE
title: "_DXVADDI_NOMINALRANGE"
author: windows-driver-content
description: The DXVADDI_NOMINALRANGE enumeration type contains values that identify whether sample data includes headroom (that is, values beyond 1.0 white) and toeroom (that is, superblacks below the reference 0.0 black).
old-location: display\dxvaddi_nominalrange.htm
old-project: display
ms.assetid: f3f5fac9-013c-4739-a29e-c781b34e5289
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DXVADDI_NominalRange_16_235, DXVADDI_NOMINALRANGE enumeration [Display Devices], DXVADDI_NOMINALRANGE, d3dumddi/DXVADDI_NOMINALRANGE, d3dumddi/DXVADDI_NominalRange_Normal, DXVADDI_NominalRange_16_235, DXVADDI_NominalRange_Normal, d3dumddi/DXVADDI_NominalRange_48_208, d3dumddi/DXVADDI_NominalRange_Unknown, d3dumddi/DXVADDI_NominalRangeMask, display.dxvaddi_nominalrange, DXVADDI_NominalRange_Unknown, DXVADDI_NominalRange_48_208, DXVA2_Structs_fee8e221-64df-474a-a178-439365c683fd.xml, _DXVADDI_NOMINALRANGE, d3dumddi/DXVADDI_NominalRange_0_255, DXVADDI_NominalRange_0_255, DXVADDI_NominalRange_Wide, d3dumddi/DXVADDI_NominalRange_Wide, DXVADDI_NominalRangeMask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
apiname:
-	DXVADDI_NOMINALRANGE
product: Windows
targetos: Windows
req.typenames: DXVADDI_NOMINALRANGE
---

# _DXVADDI_NOMINALRANGE enumeration


## -description


The DXVADDI_NOMINALRANGE enumeration type contains values that identify whether sample data includes headroom (that is, values beyond 1.0 white) and toeroom (that is, superblacks below the reference 0.0 black). 


## -syntax


````
typedef enum _DXVADDI_NOMINALRANGE { 
  DXVADDI_NominalRangeMask      = 0x07,
  DXVADDI_NominalRange_Unknown  = 0,
  DXVADDI_NominalRange_Normal   = 1,
  DXVADDI_NominalRange_Wide     = 2,
  DXVADDI_NominalRange_0_255    = 1,
  DXVADDI_NominalRange_16_235   = 2,
  DXVADDI_NominalRange_48_208   = 3
} DXVADDI_NOMINALRANGE;
````


## -enum-fields




### -field DXVADDI_NominalRangeMask

The nominal range mask. The first 3 (0x07) bits of a DWORD can be used to specify nominal range.


### -field DXVADDI_NominalRange_Unknown

The nominal range is not specified.


### -field DXVADDI_NominalRange_Normal

Normalized chroma [0..1] maps to [0..255] (8bit) or [0..1023] (10 bit).


### -field DXVADDI_NominalRange_Wide

Normalized chroma [0..1] maps to [16..235] (8bit) or [64..940] (10 bit).


### -field DXVADDI_NominalRange_0_255

Normalized chroma [0..1] maps explicitly to [0..255] (8bit).


### -field DXVADDI_NominalRange_16_235

Normalized chroma [0..1] maps explicitly to [16..235] (8bit).


### -field DXVADDI_NominalRange_48_208

Normalized chroma [0..1] maps explicitly to [48..208] (8bit).


## -remarks


One of the values of DXVADDI_NOMINALRANGE can be specified in the <b>NominalRange</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure.

Wide gamut R'G'B' (that is, blackpoint at 16,16,16 and whitepoint at 235,235,235) must be differentiated from normal <a href="http://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a>.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_NOMINALRANGE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

