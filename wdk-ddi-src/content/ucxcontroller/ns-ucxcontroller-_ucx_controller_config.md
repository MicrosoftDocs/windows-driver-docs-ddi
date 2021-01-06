---
UID: NS:ucxcontroller._UCX_CONTROLLER_CONFIG
title: _UCX_CONTROLLER_CONFIG (ucxcontroller.h)
description: This structure configuration data for a USB controller.
old-location: buses\_ucx_controller_config.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCX_CONTROLLER_CONFIG structure"]
ms.keywords: "*PUCX_CONTROLLER_CONFIG, P_UCX_CONTROLLER_CONFIG, P_UCX_CONTROLLER_CONFIG structure pointer [Buses], UCX_CONTROLLER_CONFIG, UCX_CONTROLLER_CONFIG structure [Buses], _UCX_CONTROLLER_CONFIG, buses._ucx_controller_config, ucxcontroller/P_UCX_CONTROLLER_CONFIG, ucxcontroller/_UCX_CONTROLLER_CONFIG"
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
targetos: Windows
req.typenames: UCX_CONTROLLER_CONFIG, *PUCX_CONTROLLER_CONFIG
f1_keywords:
 - _UCX_CONTROLLER_CONFIG
 - ucxcontroller/_UCX_CONTROLLER_CONFIG
 - PUCX_CONTROLLER_CONFIG
 - ucxcontroller/PUCX_CONTROLLER_CONFIG
 - UCX_CONTROLLER_CONFIG
 - ucxcontroller/UCX_CONTROLLER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucxcontroller.h
api_name:
 - UCX_CONTROLLER_CONFIG
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

A pointer to an <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_query_usb_capability">EVT_UCX_CONTROLLER_QUERY_USB_CAPABILITY</a> callback function.

### -field Reserved1

Do not use.

### -field EvtControllerGetCurrentFrameNumber

A pointer to an <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_get_current_framenumber">EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER</a> call back function.

### -field EvtControllerUsbDeviceAdd

A pointer to an <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_usbdevice_add">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> callback function.

### -field EvtControllerReset

A pointer to an <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_reset">EVT_UCX_CONTROLLER_RESET</a> callback function.

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

A pointer to an <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_get_transport_characteristics">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a> callback function.

### -field EvtControllerSetTransportCharacteristicsChangeNotification

A pointer to an <a href="/windows-hardware/drivers/ddi/ucxcontroller/nc-ucxcontroller-evt_ucx_controller_set_transport_characteristics_change_notification">EVT_UCX_CONTROLLER_SET_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION</a> callback function.

### -field Reserved5

Do not use.

### -field Reserved6

Do not use.

### -field Reserved7

Do not use.
