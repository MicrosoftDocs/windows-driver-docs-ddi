---
UID: NS:winbio_ioctl._WINBIO_BLANK_PAYLOAD
title: _WINBIO_BLANK_PAYLOAD (winbio_ioctl.h)
description: The IOCTL_BIOMETRIC_RESET and IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTLs return the WINBIO_BLANK_PAYLOAD structure as output.
old-location: biometric\winbio_blank_payload.htm
tech.root: biometric
ms.date: 02/20/2018
keywords: ["WINBIO_BLANK_PAYLOAD structure"]
ms.keywords: "*PWINBIO_BLANK_PAYLOAD, PWINBIO_BLANK_PAYLOAD, PWINBIO_BLANK_PAYLOAD structure pointer [Biometric Devices], WINBIO_BLANK_PAYLOAD, WINBIO_BLANK_PAYLOAD structure [Biometric Devices], _WINBIO_BLANK_PAYLOAD, biometric.winbio_blank_payload, biometric_ref_4a39daf0-52f5-40bf-abc6-40cd3d866f39.xml, winbio_ioctl/PWINBIO_BLANK_PAYLOAD, winbio_ioctl/WINBIO_BLANK_PAYLOAD"
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
targetos: Windows
req.typenames: WINBIO_BLANK_PAYLOAD, *PWINBIO_BLANK_PAYLOAD
f1_keywords:
 - _WINBIO_BLANK_PAYLOAD
 - winbio_ioctl/_WINBIO_BLANK_PAYLOAD
 - PWINBIO_BLANK_PAYLOAD
 - winbio_ioctl/PWINBIO_BLANK_PAYLOAD
 - WINBIO_BLANK_PAYLOAD
 - winbio_ioctl/WINBIO_BLANK_PAYLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winbio_ioctl.h
api_name:
 - _WINBIO_BLANK_PAYLOAD
 - PWINBIO_BLANK_PAYLOAD
 - WINBIO_BLANK_PAYLOAD
---

# _WINBIO_BLANK_PAYLOAD structure


## -description

The <a href="/windows-hardware/drivers/ddi/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_reset">IOCTL_BIOMETRIC_RESET</a> and <a href="/windows-hardware/drivers/ddi/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_update_firmware">IOCTL_BIOMETRIC_UPDATE_FIRMWARE</a> IOCTLs return the WINBIO_BLANK_PAYLOAD structure as output.

## -struct-fields

### -field PayloadSize

 The total size of the payload.  This includes the fixed length structure and any variable data at the end.

### -field WinBioHresult

The status detail of the I/O operation.  This is where WINBIO error and information codes will be passed. The following table shows possible values.

|Status value|Description|
|--- |--- |
|S_OK|The operation completed successfully.|
|HRESULT_FROM_NT(STATUS_IO_DEVICE_ERROR)|The driver could not gather the necessary information from the device.|
|WINBIO_E_DEVICE_BUSY|The device is in the middle of a vendor-specific operation.  This should only be returned when the device cannot be reset, and the vendor-specific operation cannot be canceled.|

