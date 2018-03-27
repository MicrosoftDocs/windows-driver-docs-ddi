---
UID: NS:ntddcdrm._CDROM_TOC_PMA_DATA
title: "_CDROM_TOC_PMA_DATA"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_PMA return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK.
old-location: storage\cdrom_toc_pma_data.htm
old-project: storage
ms.assetid: eded7fcf-8a0a-4ad2-8ce0-e10e670344a4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_TOC_PMA_DATA, CDROM_TOC_PMA_DATA, CDROM_TOC_PMA_DATA structure [Storage Devices], PCDROM_TOC_PMA_DATA, PCDROM_TOC_PMA_DATA structure pointer [Storage Devices], _CDROM_TOC_PMA_DATA, ntddcdrm/CDROM_TOC_PMA_DATA, ntddcdrm/PCDROM_TOC_PMA_DATA, storage.cdrom_toc_pma_data, structs-CD-ROM_45c0bdd5-ef51-4314-b46a-9ea66eb0b290.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	CDROM_TOC_PMA_DATA
product: Windows
targetos: Windows
req.typenames: CDROM_TOC_PMA_DATA, *PCDROM_TOC_PMA_DATA
---

# _CDROM_TOC_PMA_DATA structure


## -description


Device control IRPs with a control code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_PMA return their output data in this structure optionally followed by a series of descriptors of type CDROM_TOC_FULL_TOC_DATA_BLOCK. 


## -struct-fields




### -field Length

Indicates the length, in bytes, of the table of contents data. This length value does not include the length of the <b>Length </b>member itself. 


### -field Reserved1

Reserved.


### -field Reserved2

Reserved.


### -field Descriptors

Contains zero or more track descriptors. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff551385">CDROM_TOC_FULL_TOC_DATA_BLOCK</a> for a description of the track descriptor. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551366">CDROM_READ_TOC_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551385">CDROM_TOC_FULL_TOC_DATA_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559367">IOCTL_CDROM_READ_TOC_EX</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_PMA_DATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

