---
UID: NS:usbscan._USBSCAN_PIPE_INFORMATION
title: _USBSCAN_PIPE_INFORMATION (usbscan.h)
description: The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a USBSCAN_PIPE_CONFIGURATION structure.
tech.root: image
ms.date: 03/08/2023
keywords: ["USBSCAN_PIPE_INFORMATION structure"]
ms.keywords: "*PUSBSCAN_PIPE_INFORMATION, PUSBSCAN_PIPE_INFORMATION, PUSBSCAN_PIPE_INFORMATION structure pointer [Imaging Devices], USBSCAN_PIPE_INFORMATION, USBSCAN_PIPE_INFORMATION structure [Imaging Devices], _USBSCAN_PIPE_INFORMATION, image.usbscan_pipe_information, stifnc_3a31b5a2-4bd9-4e95-b10d-959c6caa8754.xml, usbscan/PUSBSCAN_PIPE_INFORMATION, usbscan/USBSCAN_PIPE_INFORMATION"
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
req.typenames: USBSCAN_PIPE_INFORMATION, *PUSBSCAN_PIPE_INFORMATION
f1_keywords:
 - _USBSCAN_PIPE_INFORMATION
 - usbscan/_USBSCAN_PIPE_INFORMATION
 - PUSBSCAN_PIPE_INFORMATION
 - usbscan/PUSBSCAN_PIPE_INFORMATION
 - USBSCAN_PIPE_INFORMATION
 - usbscan/USBSCAN_PIPE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - _USBSCAN_PIPE_INFORMATION
 - PUSBSCAN_PIPE_INFORMATION
 - USBSCAN_PIPE_INFORMATION
---

## -description

The **USBSCAN_PIPE_INFORMATION** structure is used to describe a USB transfer pipe for a still image device. An array of **USBSCAN_PIPE_INFORMATION** structures is supplied within a [**USBSCAN_PIPE_CONFIGURATION**](/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_pipe_configuration) structure.

## -struct-fields

### -field MaximumPacketSize

Maximum packet size for the transfer pipe.

### -field EndpointAddress

The address of the pipe's endpoint. The address is encoded as follows:

| Bits | Definition |
|---|---|
| 0..3 | Endpoint number. |
| 4..6 | Reserved, set to 0. |
| 7 | Direction, ignored for control endpoints: 0 - OUT endpoint 1 - IN endpoint |

For more information, see the *Universal Serial Bus Specification*.

### -field Interval

Polling interval, in milliseconds, for interrupt pipes. For more information, see the *Universal Serial Bus Specification*.

### -field PipeType

A [**RAW_PIPE_TYPE**](/windows-hardware/drivers/ddi/usbscan/ne-usbscan-_raw_pipe_type)-typed value identifying the pipe type.

## -see-also

[**RAW_PIPE_TYPE**](/windows-hardware/drivers/ddi/usbscan/ne-usbscan-_raw_pipe_type)

[**USBSCAN_PIPE_CONFIGURATION**](/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_pipe_configuration)
