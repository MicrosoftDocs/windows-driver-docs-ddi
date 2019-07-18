---
UID: NS:winbio_types._WINBIO_BIR
title: _WINBIO_BIR (winbio_types.h)
description: The WINBIO_BIR structure is the root of the BIR (Biometric Information Record). It contains the size and offset of any other data elements in the BIR.
old-location: biometric\winbio_bir.htm
tech.root: biometric
ms.assetid: 159d4767-b0e2-4d76-b23c-e078e13827dd
ms.date: 02/20/2018
ms.keywords: "*PWINBIO_BIR, PWINBIO_BIR, PWINBIO_BIR structure pointer [Biometric Devices], WINBIO_BIR, WINBIO_BIR structure [Biometric Devices], _WINBIO_BIR, biometric.winbio_bir, biometric_ref_95ef9f95-37c5-4f04-b4fe-05ef38b4f5f0.xml, winbio_types/PWINBIO_BIR, winbio_types/WINBIO_BIR"
ms.topic: struct
f1_keywords:
 - "winbio_types/WINBIO_BIR"
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
- WINBIO_BIR
product:
- Windows
targetos: Windows
req.typenames: WINBIO_BIR
---

# _WINBIO_BIR structure


## -description


The WINBIO_BIR structure is the root of the BIR (Biometric Information Record). It contains the size and offset of any other data elements in the BIR.


## -struct-fields




### -field HeaderBlock

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a standard biometric header. This member is required.


### -field StandardDataBlock

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a standard data block based on the ANSI 381 format. This member is optional. Set this member to 0,0 if you do not use it.


### -field VendorDataBlock

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a vendor-specific data block.  This member is optional. Set this member to 0,0 if you do not use it.


### -field SignatureBlock

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a signature block. This member is optional. Set this member to 0,0 if you do not use it.


## -remarks



The four WINBIO_BIR_DATA structures are contiguous and should be immediately followed by the actual data for each block.  Thus, the offset for the <i>HeaderBlock</i> will always be 4*(sizeof (WINBIO_BIR_DATA).  You can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_header">WINBIO_BIR_HEADER</a> structure to provide the actual data of the header block.  

The offset of where the <i>StandardDataBlock</i> starts should be the offset of the HeaderBlock plus the size of the HeaderBlock.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_data">WINBIO_BIR_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_types/ns-winbio_types-_winbio_bir_header">WINBIO_BIR_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ns-winbio_ioctl-_winbio_capture_data">WINBIO_CAPTURE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winbio_ioctl/ns-winbio_ioctl-_winbio_data">WINBIO_DATA</a>
 

 

