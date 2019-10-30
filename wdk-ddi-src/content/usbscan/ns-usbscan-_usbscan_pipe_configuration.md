---
UID: NS:usbscan._USBSCAN_PIPE_CONFIGURATION
title: _USBSCAN_PIPE_CONFIGURATION (usbscan.h)
description: The USBSCAN_PIPE_CONFIGURATION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_PIPE_CONFIGURATION.
old-location: image\usbscan_pipe_configuration.htm
tech.root: image
ms.assetid: c9b0247b-1444-46c9-a430-897594f8d223
ms.date: 05/03/2018
ms.keywords: "*PUSBSCAN_PIPE_CONFIGURATION, PUSBSCAN_PIPE_CONFIGURATION, PUSBSCAN_PIPE_CONFIGURATION structure pointer [Imaging Devices], USBSCAN_PIPE_CONFIGURATION, USBSCAN_PIPE_CONFIGURATION structure [Imaging Devices], _USBSCAN_PIPE_CONFIGURATION, image.usbscan_pipe_configuration, stifnc_b18d3edd-f392-4b68-82e4-10f870c18f6a.xml, usbscan/PUSBSCAN_PIPE_CONFIGURATION, usbscan/USBSCAN_PIPE_CONFIGURATION"
ms.topic: struct
f1_keywords:
 - "usbscan/USBSCAN_PIPE_CONFIGURATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbscan.h
api_name:
- USBSCAN_PIPE_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: USBSCAN_PIPE_CONFIGURATION, *PUSBSCAN_PIPE_CONFIGURATION
---

# _USBSCAN_PIPE_CONFIGURATION structure


## -description


The USBSCAN_PIPE_CONFIGURATION structure is used as a parameter to <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ni-usbscan-ioctl_get_pipe_configuration">IOCTL_GET_PIPE_CONFIGURATION</a>.


## -struct-fields




### -field NumberOfPipes

The number of transfer pipes supported for the device.


### -field PipeInfo

Pointer to a <b>NumberOfPipes</b>-sized array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_pipe_information">USBSCAN_PIPE_INFORMATION</a> structures.

