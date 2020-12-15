---
UID: NE:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC_PRIORITY
title: _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY (ucxendpoint.h)
description: Indicates the priority of endpoints.
old-location: buses\ucx_endpoint_characteristic_priority.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCX_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration"]
ms.keywords: UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY, UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration [Buses], UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE, _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY, buses.ucx_endpoint_characteristic_priority, ucxendpoint/UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
f1_keywords:
 - _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY
 - ucxendpoint/_UCX_ENDPOINT_CHARACTERISTIC_PRIORITY
 - UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
 - ucxendpoint/UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucxendpoint.h
api_name:
 - UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
---

# _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration


## -description

Indicates the priority of endpoints.

## -enum-fields

### -field UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE

No characteristics of the endpoint.

### -field UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO

Bulk endpoint with video has the priority.

### -field UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE

Bulk endpoint with voice has the priority.

### -field UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE

Bulk endpoint with interactive has the priority.

## -see-also

<a href="/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>
