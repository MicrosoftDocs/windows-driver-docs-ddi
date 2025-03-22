---
UID: NS:ntddvdeo._MIPI_DSI_CAPS
title: MIPI_DSI_CAPS
description: Learn more about the MIPI_DSI_CAPS structure.
tech.root: display
ms.date: 05/21/2024
keywords: ["MIPI_DSI_CAPS structure"]
f1_keywords:
 - "ntddvdeo/MIPI_DSI_CAPS"
 - "MIPI_DSI_CAPS"
ms.keywords: MIPI_DSI_CAPS, MIPI_DSI_CAPS, *PMIPI_DSI_CAPS, 
req.header: ntddvdeo.h
req.construct-type: structure
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: MIPI_DSI_CAPS, *PMIPI_DSI_CAPS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddvdeo.h
api_name: 
 - MIPI_DSI_CAPS
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# MIPI_DSI_CAPS structure (ntddvdeo.h)



## -description

The **MIPI_DSI_CAPS** structure is used to describe the capabalities and characteristics of a MIPI (mobile industry processor interface) DSI-2 (display serial interface) device.

## -struct-fields

### -field DSITypeMajor

Major version of the DSI type.

### -field DSITypeMinor

Minor version of the DSI type.

### -field SpecVersionMajor

Major version of the MIPI DSI specification.

### -field SpecVersionMinor

Minor version of the MIPI DSI specification.

### -field SpecVersionPatch

Patch level of the MIPI DSI specification.

### -field TargetMaximumReturnPacketSize

The maximum size, in bytes, of the return packet that the DSI device can handle.

### -field ResultCodeFlags

Flags that provide additional information about the result of querying the capabilities.

### -field ResultCodeStatus

The status code resulting from the query operation.

### -field Revision

Revision number of the DSI device.

### -field Level

Level of compliance or functionality of the DSI device.

### -field DeviceClassHi

High byte of the device class identifier.

### -field DeviceClassLo

Low byte of the device class identifier.

### -field ManufacturerHi

High byte of the manufacturer identifier.

### -field ManufacturerLo

Low byte of the manufacturer identifier.

### -field ProductHi

High byte of the product identifier.

### -field ProductLo

Low byte of the product identifier.

### -field LengthHi

High byte indicating the length of additional data or descriptors.

### -field LengthLo

Low byte indicating the length of additional data or descriptors.

## -remarks

## -see-also

[**IOCTL_MIPI_DSI_QUERY_CAPS**](ni-ntddvdeo-ioctl_mipi_dsi_query_caps.md)
