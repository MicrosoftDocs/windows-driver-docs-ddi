---
UID: NS:ucxusbdevice._USBDEVICE_PURGEIO
title: _USBDEVICE_PURGEIO (ucxusbdevice.h)
description: The USBDEVICE_PURGEIO structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.
old-location: buses\_usbdevice_purgeio.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBDEVICE_PURGEIO structure"]
ms.keywords: "*PUSBDEVICE_PURGEIO, P_USBDEVICE_PURGEIO, P_USBDEVICE_PURGEIO structure pointer [Buses], USBDEVICE_PURGEIO, USBDEVICE_PURGEIO structure [Buses], _USBDEVICE_PURGEIO, buses._usbdevice_purgeio, ucxusbdevice/P_USBDEVICE_PURGEIO, ucxusbdevice/_USBDEVICE_PURGEIO"
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
req.typenames: USBDEVICE_PURGEIO, *PUSBDEVICE_PURGEIO
f1_keywords:
 - _USBDEVICE_PURGEIO
 - ucxusbdevice/_USBDEVICE_PURGEIO
 - PUSBDEVICE_PURGEIO
 - ucxusbdevice/PUSBDEVICE_PURGEIO
 - USBDEVICE_PURGEIO
 - ucxusbdevice/USBDEVICE_PURGEIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - _USBDEVICE_PURGEIO
 - PUSBDEVICE_PURGEIO
 - USBDEVICE_PURGEIO
---

# _USBDEVICE_PURGEIO structure


## -description

The <b>USBDEVICE_PURGEIO</b> structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.

## -struct-fields

### -field Header

A <a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.

### -field OnSuspend

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_abortio">USBDEVICE_ABORTIO</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_startio">USBDEVICE_STARTIO</a>



<a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_tree_purgeio">USBDEVICE_TREE_PURGEIO</a>

