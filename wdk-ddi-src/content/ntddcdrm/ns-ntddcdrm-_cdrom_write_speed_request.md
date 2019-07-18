---
UID: NS:ntddcdrm._CDROM_WRITE_SPEED_REQUEST
title: _CDROM_WRITE_SPEED_REQUEST (ntddcdrm.h)
description: The CDROM_WRITE_SPEED_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE IOCTL and for requesting write speed descriptors.
old-location: storage\cdrom_write_speed_request.htm
tech.root: storage
ms.assetid: A7F8AFAE-AFFA-4022-8C04-2BF9177FE9EB
ms.date: 03/29/2018
ms.keywords: "*PCDROM_WRITE_SPEED_REQUEST, CDROM_WRITE_SPEED_REQUEST, CDROM_WRITE_SPEED_REQUEST structure [Storage Devices], PCDROM_WRITE_SPEED_REQUEST, PCDROM_WRITE_SPEED_REQUEST structure pointer [Storage Devices], _CDROM_WRITE_SPEED_REQUEST, ntddcdrm/CDROM_WRITE_SPEED_REQUEST, ntddcdrm/PCDROM_WRITE_SPEED_REQUEST, storage.cdrom_write_speed_request"
ms.topic: struct
f1_keywords:
 - "ntddcdrm/CDROM_WRITE_SPEED_REQUEST"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddcdrm.h
api_name:
- CDROM_WRITE_SPEED_REQUEST
product:
- Windows
targetos: Windows
req.typenames: CDROM_WRITE_SPEED_REQUEST, *PCDROM_WRITE_SPEED_REQUEST
---

# _CDROM_WRITE_SPEED_REQUEST structure


## -description


The <b>CDROM_WRITE_SPEED_REQUEST</b> structure is used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a> IOCTL and for requesting write speed descriptors.


## -struct-fields




### -field RequestType

As defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ne-ntddcdrm-_cdrom_performance_request_type">CDROM_PERFORMANCE_REQUEST_TYPE</a>    enumeration.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ne-ntddcdrm-_cdrom_performance_request_type">CDROM_PERFORMANCE_REQUEST_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a>
 

 

