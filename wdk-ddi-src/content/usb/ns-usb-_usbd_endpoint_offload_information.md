---
UID: NS:usb._USBD_ENDPOINT_OFFLOAD_INFORMATION
title: _USBD_ENDPOINT_OFFLOAD_INFORMATION (usb.h)
description: Stores xHCI-specific information that is used by client drivers to transfer data to and from the offloaded endpoints.
old-location: buses\usbd_endpoint_offload_information.htm
tech.root: usbref
ms.date: 01/19/2022
keywords: ["USBD_ENDPOINT_OFFLOAD_INFORMATION structure"]
ms.keywords: "*PUSBD_ENDPOINT_OFFLOAD_INFORMATION, PUSBD_ENDPOINT_OFFLOAD_INFORMATION, PUSBD_ENDPOINT_OFFLOAD_INFORMATION structure pointer [Buses], USBD_ENDPOINT_OFFLOAD_INFORMATION, USBD_ENDPOINT_OFFLOAD_INFORMATION structure [Buses], _USBD_ENDPOINT_OFFLOAD_INFORMATION, buses.usbd_endpoint_offload_information, usb/PUSBD_ENDPOINT_OFFLOAD_INFORMATION, usb/USBD_ENDPOINT_OFFLOAD_INFORMATION"
req.header: usb.h
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

# _USBD_ENDPOINT_OFFLOAD_INFORMATION structure

## -description

Stores xHCI-specific information that is used by client drivers to transfer data to and from the offloaded endpoints.

## -struct-fields

### -field Size

The size of this structure.

### -field EndpointAddress

Specifies the USB-defined endpoint address.

### -field ResourceId

The resource identifier.

### -field Mode

A [USBD_ENDPOINT_OFFLOAD_MODE](ne-usb-_usbd_endpoint_offload_mode.md)-type value that indicates whether endpoint offloading is handled in software or the USB device or host controller.

### -field RootHubPortNumber

The port number of the root hub.

### -field RouteString

The route string.

### -field Speed

The speed.

### -field UsbDeviceAddress

The USB device address.

### -field SlotId

The slot identifier.

### -field MultiTT

Transaction Translator (TT) hub.

### -field LSOrFSDeviceConnectedToTTHub

### -field Reserved0

Reserved.

### -field TransferSegmentLA

### -field TransferSegmentVA

### -field TransferRingSize

### -field TransferRingInitialCycleBit

### -field MessageNumber

### -field EventRingSegmentLA

### -field EventRingSegmentVA

### -field EventRingSize

### -field EventRingInitialCycleBit
