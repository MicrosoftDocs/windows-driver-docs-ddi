---
UID: NS:ucxusbdevice._USBDEVICE_ENABLE
title: _USBDEVICE_ENABLE (ucxusbdevice.h)
description: Contains parameters for a request to enable the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_ENABLE callback function.
old-location: buses\_usbdevice_enable.htm
tech.root: usbref
ms.assetid: DC54CC46-6ECC-4D1F-9C8C-5579EE759B6F
ms.date: 05/07/2018
ms.keywords: "*PUSBDEVICE_ENABLE, P_USBDEVICE_ENABLE, P_USBDEVICE_ENABLE structure pointer [Buses], USBDEVICE_ENABLE, USBDEVICE_ENABLE structure [Buses], _USBDEVICE_ENABLE, buses._usbdevice_enable, ucxusbdevice/P_USBDEVICE_ENABLE, ucxusbdevice/_USBDEVICE_ENABLE"
ms.topic: struct
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
- USBDEVICE_ENABLE
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_ENABLE, *PUSBDEVICE_ENABLE
---

# _USBDEVICE_ENABLE structure


## -description


Contains parameters for a request to enable the specified device. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_enable">EVT_UCX_USBDEVICE_ENABLE</a> callback function.


## -struct-fields




### -field Header

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field DefaultEndpoint

The default endpoint for the USB hub or device to enable transfers for.


### -field FailureFlags

The errors, if any, that occurred when attempting to enable the hub or device for transfers.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/ns-ucxusbdevice-_usbdevice_disable">USBDEVICE_DISABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
 

 

