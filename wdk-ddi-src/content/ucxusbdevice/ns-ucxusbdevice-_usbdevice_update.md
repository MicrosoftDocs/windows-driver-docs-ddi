---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE
title: _USBDEVICE_UPDATE (ucxusbdevice.h)
description: Passed by UCX to update the specified device. This structure is in the request parameters (Parameters.Others.Arg1) of a framework request object passed in the EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update.htm
tech.root: usbref
ms.assetid: 7E990E9A-5BF5-4D6B-A5E2-4968FBD1CEBC
ms.date: 05/07/2018
ms.keywords: "*PUSBDEVICE_UPDATE, P_USBDEVICE_UPDATE, P_USBDEVICE_UPDATE structure pointer [Buses], USBDEVICE_UPDATE, USBDEVICE_UPDATE structure [Buses], _USBDEVICE_UPDATE, buses._usbdevice_update, ucxusbdevice/P_USBDEVICE_UPDATE, ucxusbdevice/_USBDEVICE_UPDATE"
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
- USBDEVICE_UPDATE
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE, *PUSBDEVICE_UPDATE
---

# _USBDEVICE_UPDATE structure


## -description


Passed by UCX to update the specified device. This structure is in the request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object passed in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187846">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field Flags

A bitwise-OR of <a href="https://msdn.microsoft.com/library/windows/hardware/mt188083">USBDEVICE_UPDATE_FLAGS</a> values that indicates the attributes that must be updated by the client driver.


### -field DeviceDescriptor

A pointer a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a> structure that contains the device descriptor.


### -field BosDescriptor

A pointer a <b>USB_BOS_DESCRIPTOR</b> structure that contains the device descriptor. See Usbspec.h.


### -field MaxExitLatency

The maximum exit latency period.


### -field IsHub

Indicates if the USB device to update is a USB hub (TRUE) or not (FALSE).


### -field FailureFlags

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188082">USBDEVICE_UPDATE_FAILURE_FLAGS</a> structure that indicates the errors, if any, that occurred during the update operation. 


### -field Usb20HardwareLpmParameters

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188081">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>  structure that describes the Link Power Management (LPM) features.


### -field RootPortResumeTime

The resume time for the root port.


#### - USBDEVICE_MGMT_HEADER

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188081">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188082">USBDEVICE_UPDATE_FAILURE_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188083">USBDEVICE_UPDATE_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>
 

 

