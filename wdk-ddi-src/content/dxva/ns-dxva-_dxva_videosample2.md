---
UID: NS:dxva._DXVA_VideoSample2
title: "_DXVA_VideoSample2"
author: windows-driver-content
description: The DXVA_VideoSample2 structure is sent by the renderer to the driver to specify the format of a video sample.
old-location: display\dxva_videosample2.htm
old-project: display
ms.assetid: 0a82d7b4-1cba-4dd4-b5e4-ec85505ee3e1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dxva/DXVA_VideoSample2, dxvaref_4329d0c7-5dc5-42fb-b3b8-f40dc004ac17.xml, LPDXVA_VideoSample2, *LPDXVA_VideoSample2, DXVA_VideoSample2, dxva/LPDXVA_VideoSample2, LPDXVA_VideoSample2 structure pointer [Display Devices], display.dxva_videosample2, DXVA_VideoSample2 structure [Display Devices], _DXVA_VideoSample2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
apiname:
-	DXVA_VideoSample2
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample2, *LPDXVA_VideoSample2
---

# _DXVA_VideoSample2 structure


## -description


The DXVA_VideoSample2 structure is sent by the renderer to the driver to specify the format of a video sample.


## -syntax


````
typedef struct _DXVA_VideoSample2 {
#ifdef _WIN64
  DWORD            Size;
  DWORD            Reserved;
#endif 
  REFERENCE_TIME   rtStart;
  REFERENCE_TIME   rtEnd;
  DWORD            SampleFormat;
  DWORD            SampleFlags;
  VOID             *lpDDSSrcSurface;
  RECT             rcSrc;
  RECT             rcDst;
  DXVA_AYUVsample2 Palette[16];
} DXVA_VideoSample2, *LPDXVA_VideoSample2;
````


## -struct-fields




### -field Size

<b>Only compiles for a 64-bit version of the operating system.</b>

Indicates the size of this structure.


### -field Reserved

<b>Only compiles for a 64-bit version of the operating system.</b>

Reserved.


### -field rtStart

Specifies the start time of the sample.


### -field rtEnd

Specifies the end time of the sample.


### -field SampleFormat

Specifies the format of the sample as defined by values of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> enumeration type. 


### -field SampleFlags

Specifies a collection of flags that indicate changes in the current sample frame from the previous sample frame. This member is a bitwise-OR of one or more of the flags in the <a href="..\dxva\ne-dxva-_dxva_sampleflags.md">DXVA_SampleFlags</a> enumeration type.


### -field lpDDSSrcSurface

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure that represents the sample.


### -field rcSrc

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper-left and lower-right points of a rectangle on the source surface. These points define the area of the source data for the bit-block transfer and its position on the source surface.


### -field rcDst

Specifies a RECT structure that describes the upper-left and lower-right points of a rectangle on the destination surface. These points define the area in which the bit-block transfer should occur and its position on the destination surface.


### -field Palette

Specifies an array of <a href="..\dxva\ns-dxva-_dxva_ayuvsample2.md">DXVA_AYUVsample2</a> structures that represent a complete 16-color palette for palletized video substream pixel formats. The driver uses this palette to composite the substream sample. For nonpalletized pixel formats, the palette is zero and can be ignored.


## -remarks



For video substream samples, the <b>rtStart</b> and <b>rtEnd</b> members are set to 0. 

The <b>SampleFormat</b> member indicates whether the sample is a reference for a deinterlace operation or a video substream sample that must be combined with the deinterlaced video frame. The DXVA_SampleSubStream value (new for Windows Server 2003 with SP1 and later and Windows XP with SP2 and later) of the <a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a> enumeration type specifies the format for a video substream sample.

The <b>SampleFlags</b> member contains a collection of flags that indicate changes in the current sample frame from the previous sample frame. You can use these flags to optimize your driver code. In other words, your code is not required to perform operations on the current sample frame if no changes have occurred from the previous sample frame.

For information about how input samples are arranged in the array in the <b>Source</b> member of the <a href="..\dxva\ns-dxva-_dxva_deinterlacebltex.md">DXVA_DeinterlaceBltEx</a> structure, see <a href="https://msdn.microsoft.com/99110b1a-1511-44f5-a4bb-a5e38fd41fff">Input Buffer Order</a>.




## -see-also

<a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a>



<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a>



<a href="..\dxva\ne-dxva-_dxva_sampleflags.md">DXVA_SampleFlags</a>



<a href="..\dxva\ns-dxva-_dxva_deinterlacebltex.md">DXVA_DeinterlaceBltEx</a>



<a href="..\dxva\ns-dxva-_dxva_ayuvsample2.md">DXVA_AYUVsample2</a>



<a href="..\dxva\ns-dxva-_dxva_deinterlacecaps.md">DXVA_DeinterlaceCaps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoSample2 structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

