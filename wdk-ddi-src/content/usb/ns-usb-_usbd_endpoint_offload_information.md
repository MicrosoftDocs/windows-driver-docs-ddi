---
UID: NS:usb._USBD_ENDPOINT_OFFLOAD_INFORMATION
title: _USBD_ENDPOINT_OFFLOAD_INFORMATION (usb.h)
description: Stores xHCI-specific V2 information that is used by client drivers to transfer data to and from the offloaded endpoints.
old-location: buses\usbd_endpoint_offload_information.htm
tech.root: usbref
ms.date: 05/03/2024
keywords: ["USBD_ENDPOINT_OFFLOAD_INFORMATION structure"]
ms.keywords: "*PUSBD_ENDPOINT_OFFLOAD_INFORMATION, PUSBD_ENDPOINT_OFFLOAD_INFORMATION, PUSBD_ENDPOINT_OFFLOAD_INFORMATION structure pointer [Buses], USBD_ENDPOINT_OFFLOAD_INFORMATION, USBD_ENDPOINT_OFFLOAD_INFORMATION structure [Buses], _USBD_ENDPOINT_OFFLOAD_INFORMATION, buses.usbd_endpoint_offload_information, usb/PUSBD_ENDPOINT_OFFLOAD_INFORMATION, usb/USBD_ENDPOINT_OFFLOAD_INFORMATION"
ai-usage: ai-assisted
req.header: usb.h
req.construct-type: structure
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: USBD_ENDPOINT_OFFLOAD_INFORMATION, *PUSBD_ENDPOINT_OFFLOAD_INFORMATION
f1_keywords:
 - _USBD_ENDPOINT_OFFLOAD_INFORMATION
 - usb/_USBD_ENDPOINT_OFFLOAD_INFORMATION
 - PUSBD_ENDPOINT_OFFLOAD_INFORMATION
 - usb/PUSBD_ENDPOINT_OFFLOAD_INFORMATION
 - USBD_ENDPOINT_OFFLOAD_INFORMATION
 - usb/USBD_ENDPOINT_OFFLOAD_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usb.h
api_name:
 - _USBD_ENDPOINT_OFFLOAD_INFORMATION
 - PUSBD_ENDPOINT_OFFLOAD_INFORMATION
 - USBD_ENDPOINT_OFFLOAD_INFORMATION
---

# USBD_ENDPOINT_OFFLOAD_INFORMATION structure (usb.h)



## -description

Stores xHCI-specific V2 information that is used by client drivers to transfer data to and from the offloaded endpoints.

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

### -field ClientTransferRingSegmentPAIn

The physical address of the client-provided transfer ring segment.

### -field ClientTransferRingSizeIn

The size of the client-provided transfer ring segment.

### -field ClientDataBufferPAIn

The physical address of the client-provided data buffer.

### -field ClientDataBufferSizeIn

The size of the client-provided data buffer.

### -field ClientDataBufferLAOut

The physical address of the mapped data buffer.

### -field ClientDataBufferVAOut

The virtual address of the mapped data buffer.

## remarks

This structure duplicates and extends **[USBD_ENDPOINT_OFFLOAD_INFORMATION_V1](ns-usb-usbd_endpoint_offload_information_v1.md)**.

This structure supports two versions, indicated by `USBD_ENDPOINT_OFFLOAD_INFORMATION` and `USBD_ENDPOINT_OFFLOAD_INFORMATION_V2`, with the latter possibly including additional fields beyond what is documented here. The structure facilitates detailed configuration and management of USB endpoint offload.

## see-also

- **[USBD_ENDPOINT_OFFLOAD_INFORMATION_V1](ns-usb-usbd_endpoint_offload_information_v1.md)**
