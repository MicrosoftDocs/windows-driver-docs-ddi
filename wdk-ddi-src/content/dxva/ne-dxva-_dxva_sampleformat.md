---
UID: NE:dxva._DXVA_SampleFormat
title: "_DXVA_SampleFormat"
author: windows-driver-content
description: The DXVA_SampleFormat enumeration type describes the format of data that the input sample contains.
old-location: display\dxva_sampleformat.htm
tech.root: display
ms.assetid: 90cec61b-fe49-4fc7-b666-e74f745a00b1
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA_SampleFieldInterleavedEvenFirst, DXVA_SampleFieldInterleavedOddFirst, DXVA_SampleFieldSingleEven, DXVA_SampleFieldSingleOdd, DXVA_SampleFormat, DXVA_SampleFormat enumeration [Display Devices], DXVA_SampleFormatMask, DXVA_SamplePreviousFrame, DXVA_SampleProgressiveFrame, DXVA_SampleSubStream, DXVA_SampleUnknown, _DXVA_SampleFormat, display.dxva_sampleformat, dxva/DXVA_SampleFieldInterleavedEvenFirst, dxva/DXVA_SampleFieldInterleavedOddFirst, dxva/DXVA_SampleFieldSingleEven, dxva/DXVA_SampleFieldSingleOdd, dxva/DXVA_SampleFormat, dxva/DXVA_SampleFormatMask, dxva/DXVA_SamplePreviousFrame, dxva/DXVA_SampleProgressiveFrame, dxva/DXVA_SampleSubStream, dxva/DXVA_SampleUnknown, dxvaref_342ab3ab-8498-4d6f-a052-aff84c407436.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_SampleFormat
product:
- Windows
targetos: Windows
req.typenames: DXVA_SampleFormat
---

# _DXVA_SampleFormat enumeration


## -description


The DXVA_SampleFormat enumeration type describes the format of data that the input sample contains.


## -enum-fields




### -field DXVA_SampleFormatMask

Specifies the sample format mask. The first 8 (0x000000FF) bits of a DWORD can be used to specify input sample format. 



### -field DXVA_SampleUnknown

Specifies that the sample format is unknown. 



### -field DXVA_SamplePreviousFrame

Specifies that the sample contains the previous output frame.


### -field DXVA_SampleProgressiveFrame

Specifies that the sample contains a progressive frame.


### -field DXVA_SampleFieldInterleavedEvenFirst

Specifies that the sample contains two interleaved fields; the even field is temporally first.


### -field DXVA_SampleFieldInterleavedOddFirst

Specifies that the sample contains two interleaved fields; the odd field is temporally first.


### -field DXVA_SampleFieldSingleEven

Specifies that the sample contains an even interleaved field.


### -field DXVA_SampleFieldSingleOdd

Specifies that the sample contains an odd interleaved field.


### -field DXVA_SampleSubStream

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.

Specifies that the sample contains a video substream.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563967">DXVA_ExtendedFormat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564085">DXVA_VideoSample</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564092">DXVA_VideoSample2</a>
 

 

