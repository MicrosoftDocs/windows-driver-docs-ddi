---
UID: NS:ucxcontroller._UCX_CONTROLLER_CONFIG
title: "_UCX_CONTROLLER_CONFIG"
author: windows-driver-content
description: This structure configuration data for a USB controller.
old-location: buses\_ucx_controller_config.htm
old-project: usbref
ms.assetid: 9A4249B6-BFC2-42B4-BBA6-094BD78C98DE
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUCX_CONTROLLER_CONFIG, P_UCX_CONTROLLER_CONFIG, P_UCX_CONTROLLER_CONFIG structure pointer [Buses], UCX_CONTROLLER_CONFIG, UCX_CONTROLLER_CONFIG structure [Buses], _UCX_CONTROLLER_CONFIG, buses._ucx_controller_config, ucxcontroller/P_UCX_CONTROLLER_CONFIG, ucxcontroller/_UCX_CONTROLLER_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxcontroller.h
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
-	Ucxcontroller.h
api_name:
-	UCX_CONTROLLER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_CONFIG, *PUCX_CONTROLLER_CONFIG
---

# _UCX_CONTROLLER_CONFIG structure


## -description


This structure configuration data for a USB controller.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field NumberOfPresentedDeviceMgmtEvtCallbacks

The number of device event callback functions provided by this structure.


### -field EvtControllerQueryUsbCapability

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187821">EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY</a> callback function.


### -field Reserved1

Do not use.


### -field EvtControllerGetCurrentFrameNumber

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187820">EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER</a> call back function.


### -field EvtControllerUsbDeviceAdd

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187823">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> callback function.


### -field EvtControllerReset

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187822">EVT_UCX_CONTROLLER_RESET</a> callback function.


### -field Reserved2

Do not use.


### -field Reserved3

Do not use.


### -field Reserved4

Do not use.


### -field ParentBusType

The parent bus type of the USB controller.


### -field PciDeviceInfo

Information about the PCI USB controller (if present).


### -field AcpiDeviceInfo

Information about the advanced configuration and power interface (ACPI) USB controller (if present).


### -field DeviceDescription

A description for the device.


### -field ManufacturerNameString

String containing the manufacturer name.


### -field ModelNameString

String containing the model name of the controller hardware.


### -field ModelNumberString

String containing the model number of the controller hardware.


### -field EvtControllerGetTransportCharacteristics

A pointer to an <a href="https://msdn.microsoft.com/4394199C-6644-4E11-BDAF-625C2F94DEE8">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a> callback function.


### -field EvtControllerSetTransportCharacteristicsChangeNotification

A pointer to an <a href="https://msdn.microsoft.com/559D2215-B78C-41EA-9E2C-6E67AE5276BE">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> callback function.


### -field Reserved5

Do not use.


### -field Reserved6

Do not use.


### -field Reserved7

Do not use.

