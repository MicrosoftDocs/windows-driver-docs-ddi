---
UID: NS:ntddcdrm._CDROM_WRITE_SPEED_REQUEST
title: _CDROM_WRITE_SPEED_REQUEST (ntddcdrm.h)
description: The CDROM_WRITE_SPEED_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE IOCTL and for requesting write speed descriptors.
old-location: storage\cdrom_write_speed_request.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CDROM_WRITE_SPEED_REQUEST structure"]
ms.keywords: "*PCDROM_WRITE_SPEED_REQUEST, CDROM_WRITE_SPEED_REQUEST, CDROM_WRITE_SPEED_REQUEST structure [Storage Devices], PCDROM_WRITE_SPEED_REQUEST, PCDROM_WRITE_SPEED_REQUEST structure pointer [Storage Devices], _CDROM_WRITE_SPEED_REQUEST, ntddcdrm/CDROM_WRITE_SPEED_REQUEST, ntddcdrm/PCDROM_WRITE_SPEED_REQUEST, storage.cdrom_write_speed_request"
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
targetos: Windows
req.typenames: CDROM_WRITE_SPEED_REQUEST, *PCDROM_WRITE_SPEED_REQUEST
f1_keywords:
 - _CDROM_WRITE_SPEED_REQUEST
 - ntddcdrm/_CDROM_WRITE_SPEED_REQUEST
 - PCDROM_WRITE_SPEED_REQUEST
 - ntddcdrm/PCDROM_WRITE_SPEED_REQUEST
 - CDROM_WRITE_SPEED_REQUEST
 - ntddcdrm/CDROM_WRITE_SPEED_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdrm.h
api_name:
 - CDROM_WRITE_SPEED_REQUEST
---

# _CDROM_WRITE_SPEED_REQUEST structure


## -description

The <b>CDROM_WRITE_SPEED_REQUEST</b> structure is used as an input parameter to the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a> IOCTL and for requesting write speed descriptors.

## -struct-fields

### -field RequestType

As defined in the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_cdrom_performance_request_type">CDROM_PERFORMANCE_REQUEST_TYPE</a>    enumeration.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_cdrom_performance_request_type">CDROM_PERFORMANCE_REQUEST_TYPE</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a>
