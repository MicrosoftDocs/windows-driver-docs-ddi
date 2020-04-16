---
UID: NS:ucxusbdevice._USBDEVICE_DISABLE
title: _USBDEVICE_DISABLE (ucxusbdevice.h)
description: Contains parameters for a request to disable the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_DISABLE callback function.
old-location: buses\_usbdevice_disable.htm
tech.root: usbref
ms.assetid: C9F2331F-0C16-47F3-9FDE-2719E179513F
ms.date: 05/07/2018
keywords: ["_USBDEVICE_DISABLE structure"]
ms.keywords: "*PUSBDEVICE_DISABLE, P_USBDEVICE_DISABLE, P_USBDEVICE_DISABLE structure pointer [Buses], USBDEVICE_DISABLE, USBDEVICE_DISABLE structure [Buses], _USBDEVICE_DISABLE, buses._usbdevice_disable, ucxusbdevice/P_USBDEVICE_DISABLE, ucxusbdevice/_USBDEVICE_DISABLE"
f1_keywords:
 - "ucxusbdevice/USBDEVICE_DISABLE"
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
- USBDEVICE_DISABLE
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_DISABLE, *PUSBDEVICE_DISABLE
---

# _USBDEVICE_DISABLE structure


## -description


Contains parameters for a request to disable the specified device. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_disable">EVT_UCX_USBDEVICE_DISABLE</a> callback function.


## -struct-fields




### -field Header

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field DefaultEndpoint

A handle to the default endpoint of the USB device or hub to disable.

### -field UsbDeviceRecoveryAction
A [**UCX_USBDEVICE_RECOVERY_ACTION**](ne-ucxusbdevice-_ucx_usbdevice_recovery_action.md)-value that indicates FLDR or PLDR trigger resets.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_disable">EVT_UCX_USBDEVICE_DISABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_enable">USBDEVICE_ENABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
 

 

