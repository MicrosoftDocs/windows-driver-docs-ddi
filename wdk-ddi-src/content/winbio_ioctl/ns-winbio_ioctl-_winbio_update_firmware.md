---
UID: NS:winbio_ioctl._WINBIO_UPDATE_FIRMWARE
title: _WINBIO_UPDATE_FIRMWARE (winbio_ioctl.h)
description: The WINBIO_UPDATE_FIRMWARE structure is the IN payload for IOCTL_BIOMETRIC_UPDATE_FIRMWARE.
old-location: biometric\winbio_update_firmware.htm
tech.root: biometric
ms.assetid: 14775785-27e3-4bfa-ad69-695869ebb5d6
ms.date: 02/20/2018
keywords: ["_WINBIO_UPDATE_FIRMWARE structure"]
ms.keywords: "*PWINBIO_UPDATE_FIRMWARE, PWINBIO_UPDATE_FIRMWARE, PWINBIO_UPDATE_FIRMWARE structure pointer [Biometric Devices], WINBIO_UPDATE_FIRMWARE, WINBIO_UPDATE_FIRMWARE structure [Biometric Devices], _WINBIO_UPDATE_FIRMWARE, biometric.winbio_update_firmware, biometric_ref_e4f6a748-a0a4-4dcd-883a-a00e568acf7f.xml, winbio_ioctl/PWINBIO_UPDATE_FIRMWARE, winbio_ioctl/WINBIO_UPDATE_FIRMWARE"
f1_keywords:
 - "winbio_ioctl/WINBIO_UPDATE_FIRMWARE"
 - "WINBIO_UPDATE_FIRMWARE"
req.header: winbio_ioctl.h
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
- winbio_ioctl.h
api_name:
- WINBIO_UPDATE_FIRMWARE
targetos: Windows
req.typenames: WINBIO_UPDATE_FIRMWARE, *PWINBIO_UPDATE_FIRMWARE
---

# _WINBIO_UPDATE_FIRMWARE structure


## -description


The WINBIO_UPDATE_FIRMWARE structure is the IN payload for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_update_firmware">IOCTL_BIOMETRIC_UPDATE_FIRMWARE</a>.


## -struct-fields




### -field PayloadSize

Specifies the total size of the payload, which includes the fixed length structure and any variable data at the end.


### -field FirmwareData

Specifies a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_data">WINBIO_DATA</a> that contains the vendor-specific firmware image.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_update_firmware">IOCTL_BIOMETRIC_UPDATE_FIRMWARE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_blank_payload">WINBIO_BLANK_PAYLOAD</a>
 

 

