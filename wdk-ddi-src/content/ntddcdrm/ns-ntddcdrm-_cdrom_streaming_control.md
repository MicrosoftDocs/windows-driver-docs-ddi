---
UID: NS:ntddcdrm._CDROM_STREAMING_CONTROL
title: _CDROM_STREAMING_CONTROL (ntddcdrm.h)
description: The CDROM_STREAMING_CONTROL structure is used as an input parameter to the IOCTL_CDROM_ENABLE_STREAMING IOCTL.
old-location: storage\cdrom_streaming_control.htm
tech.root: storage
ms.assetid: 71D4008C-1F04-408B-93DF-DDE6FD352701
ms.date: 03/29/2018
keywords: ["_CDROM_STREAMING_CONTROL structure"]
ms.keywords: "*PCDROM_STREAMING_CONTROL, CDROM_STREAMING_CONTROL, CDROM_STREAMING_CONTROL structure [Storage Devices], PCDROM_STREAMING_CONTROL, PCDROM_STREAMING_CONTROL structure pointer [Storage Devices], _CDROM_STREAMING_CONTROL, ntddcdrm/CDROM_STREAMING_CONTROL, ntddcdrm/PCDROM_STREAMING_CONTROL, storage.cdrom_streaming_control"
f1_keywords:
 - "ntddcdrm/CDROM_STREAMING_CONTROL"
 - "CDROM_STREAMING_CONTROL"
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
- CDROM_STREAMING_CONTROL
targetos: Windows
req.typenames: CDROM_STREAMING_CONTROL, *PCDROM_STREAMING_CONTROL
---

# _CDROM_STREAMING_CONTROL structure


## -description


The <b>CDROM_STREAMING_CONTROL</b> structure is used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_enable_streaming">IOCTL_CDROM_ENABLE_STREAMING</a> IOCTL.


## -struct-fields




### -field RequestType

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_streaming_control_request_type">STREAMING_CONTROL_REQUEST_TYPE</a>   enumeration specifies the type of request.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_enable_streaming">IOCTL_CDROM_ENABLE_STREAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ne-ntddcdrm-_streaming_control_request_type">STREAMING_CONTROL_REQUEST_TYPE</a>
 

 

