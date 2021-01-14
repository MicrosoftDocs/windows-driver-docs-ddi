---
UID: NS:ucxusbdevice._USBDEVICE_ENABLE_FAILURE_FLAGS
title: _USBDEVICE_ENABLE_FAILURE_FLAGS (ucxusbdevice.h)
description: The flags that are set by the client driver in the EVT_UCX_USBDEVICE_ENABLE callback function. Indicate errors, if any, that might have occurred while enabling the device.
old-location: buses\_usbdevice_enable_failure_flags.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBDEVICE_ENABLE_FAILURE_FLAGS structure"]
ms.keywords: P_USBDEVICE_ENABLE_FAILURE_FLAGS, P_USBDEVICE_ENABLE_FAILURE_FLAGS structure pointer [Buses], USBDEVICE_ENABLE_FAILURE_FLAGS, USBDEVICE_ENABLE_FAILURE_FLAGS structure [Buses], _USBDEVICE_ENABLE_FAILURE_FLAGS, buses._usbdevice_enable_failure_flags, ucxusbdevice/P_USBDEVICE_ENABLE_FAILURE_FLAGS, ucxusbdevice/_USBDEVICE_ENABLE_FAILURE_FLAGS
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.typenames: USBDEVICE_ENABLE_FAILURE_FLAGS
f1_keywords:
 - _USBDEVICE_ENABLE_FAILURE_FLAGS
 - ucxusbdevice/_USBDEVICE_ENABLE_FAILURE_FLAGS
 - USBDEVICE_ENABLE_FAILURE_FLAGS
 - ucxusbdevice/USBDEVICE_ENABLE_FAILURE_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - _USBDEVICE_ENABLE_FAILURE_FLAGS
 - USBDEVICE_ENABLE_FAILURE_FLAGS
---

# _USBDEVICE_ENABLE_FAILURE_FLAGS structure


## -description

The flags that are set by the client driver in the  <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_enable">EVT_UCX_USBDEVICE_ENABLE</a> callback function. Indicate errors, if any, that might have occurred while enabling the device.

## -struct-fields

### -field InsufficientHardwareResourcesForDefaultEndpoint

Insufficient  hardware resources for  transfers to the default endpoint.

### -field InsufficientHardwareResourcesForDevice

Insufficient hardware resources to enable transfers.

### -field Reserved

Do not use.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_enable">EVT_UCX_USBDEVICE_ENABLE</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_enable">USBDEVICE_ENABLE</a>

