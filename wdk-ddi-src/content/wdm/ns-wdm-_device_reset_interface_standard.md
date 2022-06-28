---
UID: NS:wdm._DEVICE_RESET_INTERFACE_STANDARD
title: _DEVICE_RESET_INTERFACE_STANDARD (wdm.h)
description: The DEVICE_RESET_INTERFACE_STANDARD structure enables function drivers to reset and recover malfunctioning devices. This structure describes the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
tech.root: kernel
ms.date: 06/06/2022
keywords: ["DEVICE_RESET_INTERFACE_STANDARD structure"]
ms.keywords: "*PDEVICE_RESET_INTERFACE_STANDARD, DEVICE_RESET_INTERFACE_STANDARD, DEVICE_RESET_INTERFACE_STANDARD structure [Kernel-Mode Driver Architecture], PDEVICE_RESET_INTERFACE_STANDARD, PDEVICE_RESET_INTERFACE_STANDARD structure pointer [Kernel-Mode Driver Architecture], _DEVICE_RESET_INTERFACE_STANDARD, kernel.device_reset_interface_standard, wdm/DEVICE_RESET_INTERFACE_STANDARD, wdm/PDEVICE_RESET_INTERFACE_STANDARD"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.typenames: DEVICE_RESET_INTERFACE_STANDARD, *PDEVICE_RESET_INTERFACE_STANDARD
f1_keywords:
 - _DEVICE_RESET_INTERFACE_STANDARD
 - wdm/_DEVICE_RESET_INTERFACE_STANDARD
 - PDEVICE_RESET_INTERFACE_STANDARD
 - wdm/PDEVICE_RESET_INTERFACE_STANDARD
 - DEVICE_RESET_INTERFACE_STANDARD
 - wdm/DEVICE_RESET_INTERFACE_STANDARD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DEVICE_RESET_INTERFACE_STANDARD
 - PDEVICE_RESET_INTERFACE_STANDARD
 - DEVICE_RESET_INTERFACE_STANDARD
---

# _DEVICE_RESET_INTERFACE_STANDARD structure

## -description

The **DEVICE_RESET_INTERFACE_STANDARD** structure enables function drivers to reset and recover malfunctioning devices. This structure describes the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.

For more information see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard).

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The driver-defined interface version.

### -field Context

A pointer to interface-specific context information.

### -field InterfaceReference

A pointer to an [InterfaceReference](./nc-wdm-pinterface_reference.md) routine that increments the interface's reference count.

### -field InterfaceDereference

A pointer to an [InterfaceDereference](./nc-wdm-pinterface_dereference.md) routine that decrements the interface's reference count.

### -field DeviceReset

A pointer to the interface's [DeviceReset](./nc-wdm-device_reset_handler.md) routine. This routine can be used by function drivers to attempt to reset and recover a malfunctioning device.

### -field SupportedResetTypes

Defines the **ULONG** parameter *SupportedResetTypes*.

### -field Reserved

Reserved for future use.

### -field QueryBusSpecificResetInfo

Defines the **PDEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER** parameter *QueryBusSpecificResetInfo*.

### -field DeviceBusSpecificReset

Defines the **PDEVICE_BUS_SPECIFIC_RESET_HANDLER** parameter *DeviceBusSpecificReset*.

### -field GetDeviceResetStatus

Defines the **PGET_DEVICE_RESET_STATUS** parameter *GetDeviceResetStatus*.

## -remarks

The **DEVICE_RESET_INTERFACE_STANDARD** structure is an extension of the [INTERFACE](./ns-wdm-_interface.md) structure. A driver obtains a pointer to the **DEVICE_RESET_INTERFACE_STANDARD** structure by sending an [IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface) IRP to its bus driver with **InterfaceType** set to GUID_DEVICE_RESET_INTERFACE_STANDARD.

For more information about the purpose of this interface, see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard).

## -see-also

[DeviceReset](./nc-wdm-device_reset_handler.md)

[INTERFACE](./ns-wdm-_interface.md)

[IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface)

[InterfaceDereference](./nc-wdm-pinterface_dereference.md)

[InterfaceReference](./nc-wdm-pinterface_reference.md)