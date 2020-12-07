---
UID: NS:ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
title: _UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY (ucxusbdevice.h)
description: Stores the isochronous transfer path delay values.
old-location: buses\ucx_usbdevice_characteristic_path_delay.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY structure"]
ms.keywords: "*PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY, PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY, PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY structure pointer [Buses], UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY, UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY structure [Buses], _UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY, buses.ucx_usbdevice_characteristic_path_delay, ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY"
req.header: ucxusbdevice.h
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
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY, *PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
f1_keywords:
 - _UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
 - ucxusbdevice/_UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
 - PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
 - ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
 - UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
 - ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucxusbdevice.h
api_name:
 - UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY
---

# _UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY structure


## -description

Stores the isochronous transfer path delay values.

## -struct-fields

### -field MaximumSendPathDelayInMilliSeconds

The maximum delay in milliseconds from the time the  client driver's isochronous transfer is received by the USB driver stack to the time the transfer is programmed in the host controller. The host controller could either be a local host (as in case of wired USB) or it could be a remote controller as in case of Media-Agnostic USB (MA-USB). In case of MA-USB, it includes the maximum delay associated with the network medium.

### -field MaximumCompletionPathDelayInMilliSeconds

The maximum delay in milliseconds from the time an isochronous transfer is completed by the (local or remote) host controller to the time the corresponding client driver's request is completed by the USB driver stack. For MA-USB, it includes the maximum delay associated with the network medium.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>
