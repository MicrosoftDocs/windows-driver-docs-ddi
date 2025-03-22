---
UID: NS:usb._USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
tech.root: usbref
title: USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
ms.date: 05/15/2024
targetos: Windows
description: Stores xHCI-specific V1 information that is used by client drivers to transfer data to and from the offloaded endpoints.
prerelease: false
ai-usage: ai-assisted
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: usb.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: USBD_ENDPOINT_OFFLOAD_INFORMATION_V1, *PUSBD_ENDPOINT_OFFLOAD_INFORMATION_V1
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usb.h
api_name:
 - _USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - PUSBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
f1_keywords:
 - _USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - usb/_USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - PUSBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - usb/PUSBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
 - usb/USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
dev_langs:
 - c++
helpviewer_keywords:
 - _USBD_ENDPOINT_OFFLOAD_INFORMATION_V1
---

# USBD_ENDPOINT_OFFLOAD_INFORMATION_V1 structure (usb.h)

## -description

Stores xHCI-specific V1 information that is used by client drivers to transfer data to and from the offloaded endpoints.

## -struct-fields

### -field Size

The size of this structure.

### -field EndpointAddress

Specifies the USB-defined endpoint address.

### -field ResourceId

The resource identifier.

### -field Mode

A **[USBD_ENDPOINT_OFFLOAD_MODE](ne-usb-_usbd_endpoint_offload_mode.md)** value that indicates whether endpoint offloading is handled in software or the USB device or host controller.

### -field RootHubPortNumber

The port number of the root hub to which the device is connected.

### -field RouteString

The route string describing the path from the root hub to the device.

### -field Speed

The speed of the USB device.

### -field UsbDeviceAddress

The USB address of the device.

### -field SlotId

The slot ID of the device.

### -field MultiTT

Indicates if the device is connected to a hub with transaction translators.

### -field LSOrFSDeviceConnectedToTTHub

Indicates if the device is a low-speed or full-speed device connected to a hub with transaction translators.

### -field Reserved0

Reserved.

### -field TransferSegmentLA

The physical address of the transfer ring segment.

### -field TransferSegmentVA

The virtual address of the transfer ring segment.

### -field TransferRingSize

The size of the transfer ring.

### -field TransferRingInitialCycleBit

The initial cycle bit of the transfer ring.

### -field MessageNumber

The message number for the secondary event ring.

### -field EventRingSegmentLA

The physical address of the event ring segment.

### -field EventRingSegmentVA

The virtual address of the event ring segment.

### -field EventRingSize

The size of the event ring, in bytes.

### -field EventRingInitialCycleBit

The initial cycle bit of the event ring.

## see-also

- **[USBD_ENDPOINT_OFFLOAD_INFORMATION](ns-usb-_usbd_endpoint_offload_information.md)**
