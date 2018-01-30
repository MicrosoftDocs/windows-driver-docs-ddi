---
UID: NE:d3dumddi._DXVADDI_SAMPLEFORMAT
title: "_DXVADDI_SAMPLEFORMAT"
author: windows-driver-content
description: The DXVADDI_SAMPLEFORMAT enumeration type contains values that identify how a video frame is sampled.
old-location: display\dxvaddi_sampleformat.htm
old-project: display
ms.assetid: 23482cdc-6412-4309-805e-a439d8e81b59
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DXVADDI_SampleProgressiveFrame, DXVADDI_SampleFieldSingleEven, d3dumddi/DXVADDI_SampleFieldInterleavedOddFirst, d3dumddi/DXVADDI_SampleFieldInterleavedEvenFirst, d3dumddi/DXVADDI_SampleFieldSingleOdd, DXVADDI_SAMPLEFORMAT enumeration [Display Devices], _DXVADDI_SAMPLEFORMAT, d3dumddi/DXVADDI_SampleFieldSingleEven, d3dumddi/DXVADDI_SampleSubStream, DXVADDI_SampleFormatMask, display.dxvaddi_sampleformat, DXVADDI_SampleFieldInterleavedEvenFirst, DXVADDI_SampleSubStream, DXVADDI_SampleProgressiveFrame, DXVADDI_SAMPLEFORMAT, DXVADDI_SampleFieldSingleOdd, d3dumddi/DXVADDI_SampleFormatMask, d3dumddi/DXVADDI_SAMPLEFORMAT, DXVADDI_SampleFieldInterleavedOddFirst, DXVA2_Structs_70e0302d-16a1-4a48-8f51-943873c20997.xml, DXVADDI_SampleUnknown, d3dumddi/DXVADDI_SampleUnknown
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
-	DXVADDI_SAMPLEFORMAT
product: Windows
targetos: Windows
req.typenames: DXVADDI_SAMPLEFORMAT
---

# _DXVADDI_SAMPLEFORMAT enumeration


## -description


The DXVADDI_SAMPLEFORMAT enumeration type contains values that identify how a video frame is sampled.


## -syntax


````
typedef enum _DXVADDI_SAMPLEFORMAT { 
  DXVADDI_SampleFormatMask                 = 0x00FF,
  DXVADDI_SampleUnknown                    = 0,
  DXVADDI_SampleProgressiveFrame           = 2,
  DXVADDI_SampleFieldInterleavedEvenFirst  = 3,
  DXVADDI_SampleFieldInterleavedOddFirst   = 4,
  DXVADDI_SampleFieldSingleEven            = 5,
  DXVADDI_SampleFieldSingleOdd             = 6,
  DXVADDI_SampleSubStream                  = 7
} DXVADDI_SAMPLEFORMAT;
````


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


One of the values of DXVADDI_SAMPLEFORMAT can be specified in the <b>SampleFormat</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_SAMPLEFORMAT enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

