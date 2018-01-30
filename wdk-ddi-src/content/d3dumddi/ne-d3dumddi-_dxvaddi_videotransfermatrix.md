---
UID: NE:d3dumddi._DXVADDI_VIDEOTRANSFERMATRIX
title: "_DXVADDI_VIDEOTRANSFERMATRIX"
author: windows-driver-content
description: The DXVADDI_VIDEOTRANSFERMATRIX enumeration type contains values that identify the conversion matrix from Y'Cb'Cr' to (studio) R'G'B'.
old-location: display\dxvaddi_videotransfermatrix.htm
old-project: display
ms.assetid: ef1f3c9b-70e5-48bd-b9f4-60ec661dc880
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DXVADDI_VideoTransferMatrixMask, d3dumddi/DXVADDI_VideoTransferMatrix_BT709, d3dumddi/DXVADDI_VideoTransferMatrix_SMPTE240M, d3dumddi/DXVADDI_VideoTransferMatrix_BT601, DXVADDI_VIDEOTRANSFERMATRIX, display.dxvaddi_videotransfermatrix, DXVA2_Structs_af3c1fd4-43c5-4700-b88e-46f54feed5d2.xml, DXVADDI_VideoTransferMatrix_SMPTE240M, d3dumddi/DXVADDI_VideoTransferMatrix_Unknown, DXVADDI_VideoTransferMatrix_BT709, DXVADDI_VideoTransferMatrix_BT601, DXVADDI_VIDEOTRANSFERMATRIX enumeration [Display Devices], DXVADDI_VideoTransferMatrixMask, DXVADDI_VideoTransferMatrix_Unknown, _DXVADDI_VIDEOTRANSFERMATRIX, d3dumddi/DXVADDI_VIDEOTRANSFERMATRIX
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
-	DXVADDI_VIDEOTRANSFERMATRIX
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOTRANSFERMATRIX
---

# _DXVADDI_VIDEOTRANSFERMATRIX enumeration


## -description


The DXVADDI_VIDEOTRANSFERMATRIX enumeration type contains values that identify the conversion matrix from Y'Cb'Cr' to (studio) R'G'B'.


## -syntax


````
typedef enum _DXVADDI_VIDEOTRANSFERMATRIX { 
  DXVADDI_VideoTransferMatrixMask        = 0x07,
  DXVADDI_VideoTransferMatrix_Unknown    = 0,
  DXVADDI_VideoTransferMatrix_BT709      = 1,
  DXVADDI_VideoTransferMatrix_BT601      = 2,
  DXVADDI_VideoTransferMatrix_SMPTE240M  = 3
} DXVADDI_VIDEOTRANSFERMATRIX;
````


## -enum-fields




### -field DXVADDI_VideoTransferMatrixMask

Specifies the video transfer matrix mask. The first 3 (0x07) bits of a DWORD can be used to specify video transfer matrix.


### -field DXVADDI_VideoTransferMatrix_Unknown

Specifies that the video transfer matrix is not specified. The default value is BT601 for standard definition (SD) video and BT709 for high definition (HD) video.


### -field DXVADDI_VideoTransferMatrix_BT709

Specifies the BT709 transfer matrix.


### -field DXVADDI_VideoTransferMatrix_BT601

Specifies the BT601 transfer matrix.


### -field DXVADDI_VideoTransferMatrix_SMPTE240M

Specifies a HD video standard that is rarely used in Japan.


## -remarks


One of the values of DXVADDI_VIDEOTRANSFERMATRIX can be specified in the <b>VideoTransferMatrix</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOTRANSFERMATRIX enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

