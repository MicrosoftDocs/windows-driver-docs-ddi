---
UID: NE:dxva._DXVA_VideoTransferMatrix
title: _DXVA_VideoTransferMatrix (dxva.h)
description: The DXVA_VideoTransferMatrix enumeration type contains enumerators that identify the conversion matrix from Y'Cb'Cr' to R'G'B'.
old-location: display\dxva_videotransfermatrix.htm
tech.root: display
ms.assetid: 726ce165-fd07-4dd3-a004-8081481340a1
ms.date: 05/10/2018
keywords: ["_DXVA_VideoTransferMatrix enumeration"]
ms.keywords: DXVA_VideoTransferMatrix, DXVA_VideoTransferMatrix enumeration [Display Devices], DXVA_VideoTransferMatrixMask, DXVA_VideoTransferMatrixShift, DXVA_VideoTransferMatrix_BT601, DXVA_VideoTransferMatrix_BT709, DXVA_VideoTransferMatrix_SMPTE240M, DXVA_VideoTransferMatrix_Unknown, _DXVA_VideoTransferMatrix, display.dxva_videotransfermatrix, dxva/DXVA_VideoTransferMatrix, dxva/DXVA_VideoTransferMatrixMask, dxva/DXVA_VideoTransferMatrixShift, dxva/DXVA_VideoTransferMatrix_BT601, dxva/DXVA_VideoTransferMatrix_BT709, dxva/DXVA_VideoTransferMatrix_SMPTE240M, dxva/DXVA_VideoTransferMatrix_Unknown, dxvaref_82624d1d-650f-41a2-a8d2-fb8c9936caab.xml
f1_keywords:
 - "dxva/DXVA_VideoTransferMatrix"
 - "DXVA_VideoTransferMatrix"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
- dxva.h
api_name:
- DXVA_VideoTransferMatrix
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoTransferMatrix
---

# _DXVA_VideoTransferMatrix enumeration


## -description


The DXVA_VideoTransferMatrix enumeration type contains enumerators that identify the conversion matrix from Y'Cb'Cr' to R'G'B'.


## -enum-fields




### -field DXVA_VideoTransferMatrixShift

Specifies to shift bits by 15 positions (DXVA_ExtColorData_ShiftBase + 7, or 8 + 7).


### -field DXVA_VideoTransferMatrixMask

Specifies the video transfer matrix mask. 3 (0x00038000) bits of a DWORD can be used to specify video transfer matrix.


### -field DXVA_VideoTransferMatrix_Unknown

Specifies that the video transfer matrix is not specified. The default is BT601 for standard definition (SD) video and BT709 for high definition (HD) video.


### -field DXVA_VideoTransferMatrix_BT709

Specifies the BT709 transfer matrix.


### -field DXVA_VideoTransferMatrix_BT601

Specifies the BT601 transfer matrix.


### -field DXVA_VideoTransferMatrix_SMPTE240M

Specifies a HD video standard rarely used in Japan.


## -remarks



One of the enumerators of DXVA_VideoTransferMatrix can be specified in the <b>VideoTransferMatrix</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_extendedformat">DXVA_ExtendedFormat</a>
 

 

