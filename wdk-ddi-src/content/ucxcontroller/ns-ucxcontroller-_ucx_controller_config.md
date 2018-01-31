---
UID: NS:ucxcontroller._UCX_CONTROLLER_CONFIG
title: "_UCX_CONTROLLER_CONFIG"
author: windows-driver-content
description: This structure configuration data for a USB controller.
old-location: buses\_ucx_controller_config.htm
old-project: usbref
ms.assetid: 9A4249B6-BFC2-42B4-BBA6-094BD78C98DE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UCX_CONTROLLER_CONFIG structure [Buses], P_UCX_CONTROLLER_CONFIG, ucxcontroller/_UCX_CONTROLLER_CONFIG, *PUCX_CONTROLLER_CONFIG, _UCX_CONTROLLER_CONFIG, buses._ucx_controller_config, ucxcontroller/P_UCX_CONTROLLER_CONFIG, UCX_CONTROLLER_CONFIG, P_UCX_CONTROLLER_CONFIG structure pointer [Buses]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucxcontroller.h
apiname:
-	UCX_CONTROLLER_CONFIG
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_CONFIG, *PUCX_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_CONFIG structure


## -description


This structure configuration data for a USB controller.


## -syntax


````
typedef struct _UCX_CONTROLLER_CONFIG {
   ULONG                                                                   Size;
  ULONG                                                                    NumberOfPresentedDeviceMgmtEvtCallbacks;
  PFN_UCX_CONTROLLER_QUERY_USB_CAPABILITY                                  EvtControllerQueryUsbCapability;
  HANDLE                                                                   Reserved1;
  PFN_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER                               EvtControllerGetCurrentFrameNumber;
  PFN_UCX_CONTROLLER_USBDEVICE_ADD                                         EvtControllerUsbDeviceAdd;
  PFN_UCX_CONTROLLER_RESET                                                 EvtControllerReset;
  HANDLE                                                                   Reserved2;
  HANDLE                                                                   Reserved3;
  HANDLE                                                                   Reserved4;
  UCX_CONTROLLER_PARENT_BUS_TYPE                                           ParentBusType;
  UCX_CONTROLLER_PCI_INFORMATION                                           PciDeviceInfo;
  UCX_CONTROLLER_ACPI_INFORMATION                                          AcpiDeviceInfo;
  UCHAR                                                                    DeviceDescription[MAX_GENERIC_USB_CONTROLLER_NAME_SIZE];
  UNICODE_STRING                                                           ManufacturerNameString;
  UNICODE_STRING                                                           ModelNameString;
  UNICODE_STRING                                                           ModelNumberString;
      PFN_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS                     EvtControllerGetTransportCharacteristics;
      PFN_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION EvtControllerSetTransportCharacteristicsChangeNotification;
  HANDLE                                                                   Reserved5;
  HANDLE                                                                   Reserved6;
  HANDLE                                                                   Reserved7;
} UCX_CONTROLLER_CONFIG, *P_UCX_CONTROLLER_CONFIG;
````


## -struct-fields




#### - Size

The size in bytes of this structure.


#### - NumberOfPresentedDeviceMgmtEvtCallbacks

The number of device event callback functions provided by this structure.


#### - EvtControllerQueryUsbCapability

A pointer to an <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_query_usb_capability.md">EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY</a> callback function.


#### - Reserved1

Do not use.


#### - EvtControllerGetCurrentFrameNumber

A pointer to an <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_get_current_framenumber.md">EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER</a> call back function.


#### - EvtControllerUsbDeviceAdd

A pointer to an <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> callback function.


#### - EvtControllerReset

A pointer to an <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_reset.md">EVT_UCX_CONTROLLER_RESET</a> callback function.


#### - Reserved2

Do not use.


#### - Reserved3

Do not use.


#### - Reserved4

Do not use.


#### - ParentBusType

The parent bus type of the USB controller.


#### - PciDeviceInfo

Information about the PCI USB controller (if present).


#### - AcpiDeviceInfo

Information about the advanced configuration and power interface (ACPI) USB controller (if present).


#### - DeviceDescription

A description for the device.


#### - ManufacturerNameString

String containing the manufacturer name.


#### - ModelNameString

String containing the model name of the controller hardware.


#### - ModelNumberString

String containing the model number of the controller hardware.


#### - EvtControllerGetTransportCharacteristics

A pointer to an <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics.md">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a> callback function.


#### - EvtControllerSetTransportCharacteristicsChangeNotification

A pointer to an <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_set_transport_characteristics_change_notification.md">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> callback function.


#### - Reserved5

Do not use.


#### - Reserved6

Do not use.


#### - Reserved7

Do not use.

