---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE
title: "_USBDEVICE_UPDATE"
author: windows-driver-content
description: Passed by UCX to update the specified device. This structure is in the request parameters (Parameters.Others.Arg1) of a framework request object passed in the EVT_UCX_USBDEVICE_UPDATE callback function.
old-location: buses\_usbdevice_update.htm
old-project: usbref
ms.assetid: 7E990E9A-5BF5-4D6B-A5E2-4968FBD1CEBC
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBDEVICE_UPDATE, P_USBDEVICE_UPDATE, P_USBDEVICE_UPDATE structure pointer [Buses], USBDEVICE_UPDATE, USBDEVICE_UPDATE structure [Buses], _USBDEVICE_UPDATE, buses._usbdevice_update, ucxusbdevice/P_USBDEVICE_UPDATE, ucxusbdevice/_USBDEVICE_UPDATE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	USBDEVICE_UPDATE
product: Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE, *PUSBDEVICE_UPDATE
req.product: Windows 10 or later.
---

# _USBDEVICE_UPDATE structure


## -description


Passed by UCX to update the specified device. This structure is in the request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object passed in the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_update.md">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


## -syntax


````
typedef struct _USBDEVICE_UPDATE {
#if _cplusplus
  USBDEVICE_MGMT_HEADER                       Header;
#else 
                                              USBDEVICE_MGMT_HEADER;
#endif 
  USBDEVICE_UPDATE_FLAGS                      Flags;
  PUSB_DEVICE_DESCRIPTOR                      DeviceDescriptor;
  USB_BOS_DESCRIPTOR                          BosDescriptor;
  ULONG                                       MaxExitLatency;
  BOOLEAN                                     IsHub;
  USBDEVICE_UPDATE_FAILURE_FLAGS              FailureFlags;
  USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS Usb20HardwareLpmParameters;
  USHORT                                      RootPortResumeTime;
#endif 
} USBDEVICE_UPDATE, *P_USBDEVICE_UPDATE;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field Flags

A bitwise-OR of <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_flags.md">USBDEVICE_UPDATE_FLAGS</a> values that indicates the attributes that must be updated by the client driver.


### -field DeviceDescriptor

A pointer a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> structure that contains the device descriptor.


### -field BosDescriptor

A pointer a <b>USB_BOS_DESCRIPTOR</b> structure that contains the device descriptor. See Usbspec.h.


### -field MaxExitLatency

The maximum exit latency period.


### -field IsHub

Indicates if the USB device to update is a USB hub (TRUE) or not (FALSE).


### -field FailureFlags

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_failure_flags.md">USBDEVICE_UPDATE_FAILURE_FLAGS</a> structure that indicates the errors, if any, that occurred during the update operation. 


### -field Usb20HardwareLpmParameters

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>  structure that describes the Link Power Management (LPM) features.


### -field RootPortResumeTime

The resume time for the root port.


#### - USBDEVICE_MGMT_HEADER

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_failure_flags.md">USBDEVICE_UPDATE_FAILURE_FLAGS</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_flags.md">USBDEVICE_UPDATE_FLAGS</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



 

 


