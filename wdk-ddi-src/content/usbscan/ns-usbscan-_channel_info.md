---
UID: NS:usbscan._CHANNEL_INFO
title: _CHANNEL_INFO (usbscan.h)
description: The CHANNEL_INFO structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_CHANNEL_ALIGN_RQST.
old-location: image\channel_info.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["CHANNEL_INFO structure"]
ms.keywords: "*PCHANNEL_INFO, CHANNEL_INFO, CHANNEL_INFO structure [Imaging Devices], PCHANNEL_INFO, PCHANNEL_INFO structure pointer [Imaging Devices], _CHANNEL_INFO, image.channel_info, stifnc_f0aea91c-5d41-43e5-bb8b-139bfb7c3198.xml, usbscan/CHANNEL_INFO, usbscan/PCHANNEL_INFO"
req.header: usbscan.h
req.include-header: Usbscan.h
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
req.typenames: CHANNEL_INFO, *PCHANNEL_INFO
f1_keywords:
 - _CHANNEL_INFO
 - usbscan/_CHANNEL_INFO
 - PCHANNEL_INFO
 - usbscan/PCHANNEL_INFO
 - CHANNEL_INFO
 - usbscan/CHANNEL_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - _CHANNEL_INFO
 - PCHANNEL_INFO
 - CHANNEL_INFO
---

# _CHANNEL_INFO structure


## -description

The CHANNEL_INFO structure is used as a parameter to <a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_get_channel_align_rqst">IOCTL_GET_CHANNEL_ALIGN_RQST</a>.

## -struct-fields

### -field EventChannelSize

Maximum packet size for the interrupt transfer pipe.

### -field uReadDataAlignment

Maximum packet size for the bulk IN transfer pipe.

### -field uWriteDataAlignment

Maximum packet size for the bulk OUT transfer pipe.

