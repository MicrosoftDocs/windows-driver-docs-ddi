---
UID: NS:ucxusbdevice._UCXUSBDEVICE_INFO
title: _UCXUSBDEVICE_INFO (ucxusbdevice.h)
description: Contains information about the USB device. This structure is passed by UCX in the EVT_UCX_CONTROLLER_USBDEVICE_ADD event callback function.
old-location: buses\_ucxusbdevice_info.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCXUSBDEVICE_INFO structure"]
ms.keywords: "*PUCXUSBDEVICE_INFO, P_UCXUSBDEVICE_INFO, P_UCXUSBDEVICE_INFO structure pointer [Buses], UCXUSBDEVICE_INFO, UCXUSBDEVICE_INFO structure [Buses], _UCXUSBDEVICE_INFO, buses._ucxusbdevice_info, ucxusbdevice/P_UCXUSBDEVICE_INFO, ucxusbdevice/_UCXUSBDEVICE_INFO"
req.header: ucxusbdevice.h
req.include-header: Ucxusbdevice.h
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
req.typenames: UCXUSBDEVICE_INFO, *PUCXUSBDEVICE_INFO
f1_keywords:
 - _UCXUSBDEVICE_INFO
 - ucxusbdevice/_UCXUSBDEVICE_INFO
 - PUCXUSBDEVICE_INFO
 - ucxusbdevice/PUCXUSBDEVICE_INFO
 - UCXUSBDEVICE_INFO
 - ucxusbdevice/UCXUSBDEVICE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - _UCXUSBDEVICE_INFO
 - PUCXUSBDEVICE_INFO
 - UCXUSBDEVICE_INFO
---

# _UCXUSBDEVICE_INFO structure


## -description

Contains information about the USB device. This structure is passed by UCX in the <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_usbdevice_add">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> event callback function.

## -struct-fields

### -field Size

The size in bytes of this structure.

### -field DeviceSpeed

Defines the device speed of the USB device or hub.

### -field TtHub

A handle to the USB  device object that represents the TT hub.

### -field PortPath

The port path for the USB device or hub.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_usbdevice_add">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>

