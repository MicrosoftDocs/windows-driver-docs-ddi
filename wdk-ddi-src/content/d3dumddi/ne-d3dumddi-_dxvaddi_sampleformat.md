---
UID: NE:d3dumddi._DXVADDI_SAMPLEFORMAT
title: _DXVADDI_SAMPLEFORMAT (d3dumddi.h)
description: The DXVADDI_SAMPLEFORMAT enumeration type contains values that identify how a video frame is sampled.
old-location: display\dxvaddi_sampleformat.htm
tech.root: display
ms.assetid: 23482cdc-6412-4309-805e-a439d8e81b59
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_70e0302d-16a1-4a48-8f51-943873c20997.xml, DXVADDI_SAMPLEFORMAT, DXVADDI_SAMPLEFORMAT enumeration [Display Devices], DXVADDI_SampleFieldInterleavedEvenFirst, DXVADDI_SampleFieldInterleavedOddFirst, DXVADDI_SampleFieldSingleEven, DXVADDI_SampleFieldSingleOdd, DXVADDI_SampleFormatMask, DXVADDI_SampleProgressiveFrame, DXVADDI_SampleSubStream, DXVADDI_SampleUnknown, _DXVADDI_SAMPLEFORMAT, d3dumddi/DXVADDI_SAMPLEFORMAT, d3dumddi/DXVADDI_SampleFieldInterleavedEvenFirst, d3dumddi/DXVADDI_SampleFieldInterleavedOddFirst, d3dumddi/DXVADDI_SampleFieldSingleEven, d3dumddi/DXVADDI_SampleFieldSingleOdd, d3dumddi/DXVADDI_SampleFormatMask, d3dumddi/DXVADDI_SampleProgressiveFrame, d3dumddi/DXVADDI_SampleSubStream, d3dumddi/DXVADDI_SampleUnknown, display.dxvaddi_sampleformat
ms.topic: enum
f1_keywords:
 - "d3dumddi/DXVADDI_SAMPLEFORMAT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- DXVADDI_SAMPLEFORMAT
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_SAMPLEFORMAT
---

# _DXVADDI_SAMPLEFORMAT enumeration


## -description


The DXVADDI_SAMPLEFORMAT enumeration type contains values that identify how a video frame is sampled.


## -enum-fields




### -field DXVADDI_SampleFormatMask

The sample format mask. The first 8 (0xFF) bits of a DWORD can be used to specify input sample format.


### -field DXVADDI_SampleUnknown

The sample format is unknown.


### -field DXVADDI_SampleProgressiveFrame

The sample contains a progressive frame.


### -field DXVADDI_SampleFieldInterleavedEvenFirst

The sample contains two interleaved fields; the even field is temporally first.


### -field DXVADDI_SampleFieldInterleavedOddFirst

The sample contains two interleaved fields; the odd field is temporally first.


### -field DXVADDI_SampleFieldSingleEven

The sample contains an even interleaved field.


### -field DXVADDI_SampleFieldSingleOdd

The sample contains an odd interleaved field.


### -field DXVADDI_SampleSubStream

The sample contains a video substream.


## -remarks



One of the values of DXVADDI_SAMPLEFORMAT can be specified in the <b>SampleFormat</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>
 

 

