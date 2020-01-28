---
UID: NS:ucxusbdevice._USBDEVICE_ABORTIO
title: _USBDEVICE_ABORTIO (ucxusbdevice.h)
description: Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers.
old-location: buses\_usbdevice_abortio.htm
tech.root: usbref
ms.assetid: 69720940-4D3E-43E6-B587-427ED2049FCC
ms.date: 05/07/2018
ms.keywords: "*PUSBDEVICE_ABORTIO, P_USBDEVICE_ABORTIO, P_USBDEVICE_ABORTIO structure pointer [Buses], USBDEVICE_ABORTIO, USBDEVICE_ABORTIO structure [Buses], _USBDEVICE_ABORTIO, buses._usbdevice_abortio, ucxusbdevice/P_USBDEVICE_ABORTIO, ucxusbdevice/_USBDEVICE_ABORTIO"
f1_keywords:
 - "ucxusbdevice/USBDEVICE_ABORTIO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxusbdevice.h
api_name:
- USBDEVICE_ABORTIO
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_ABORTIO, *PUSBDEVICE_ABORTIO
---

# _USBDEVICE_ABORTIO structure


## -description


Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers. 


## -struct-fields




### -field Header

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_purgeio">USBDEVICE_PURGEIO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_startio">USBDEVICE_STARTIO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
 

 

