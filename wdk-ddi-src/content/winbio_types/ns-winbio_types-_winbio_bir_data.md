---
UID: NS:winbio_types._WINBIO_BIR_DATA
title: _WINBIO_BIR_DATA (winbio_types.h)
description: The WINBIO_BIR_DATA structure contains the location and size of a block in a BIR. The offset is measured from the beginning of the WINBIO_BIR structure.
old-location: biometric\winbio_bir_data.htm
tech.root: biometric
ms.assetid: c9ce383e-277d-4fed-839b-8539554f654c
ms.date: 02/20/2018
ms.keywords: "*PWINBIO_BIR_DATA, PWINBIO_BIR_DATA, PWINBIO_BIR_DATA structure pointer [Biometric Devices], WINBIO_BIR_DATA, WINBIO_BIR_DATA structure [Biometric Devices], _WINBIO_BIR_DATA, biometric.winbio_bir_data, biometric_ref_8f527949-820e-416e-952d-8dd3bdf543f6.xml, winbio_types/PWINBIO_BIR_DATA, winbio_types/WINBIO_BIR_DATA"
ms.topic: struct
f1_keywords:
 - "winbio_types/WINBIO_BIR_DATA"
req.header: winbio_types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
- winbio_types.h
api_name:
- WINBIO_BIR_DATA
product:
- Windows
targetos: Windows
req.typenames: WINBIO_BIR_DATA
---

# _WINBIO_BIR_DATA structure


## -description


The WINBIO_BIR_DATA structure contains the location and size of a block in a BIR. The offset is measured from the beginning of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir">WINBIO_BIR</a> structure.


## -struct-fields




### -field Size

Specifies the size, in bytes, of a block in the BIR.


### -field Offset

Specifies the offset, in bytes, of the block within the BIR.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_header">WINBIO_BIR_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ns-winbio_ioctl-_winbio_capture_data">WINBIO_CAPTURE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ns-winbio_ioctl-_winbio_data">WINBIO_DATA</a>
 

 

