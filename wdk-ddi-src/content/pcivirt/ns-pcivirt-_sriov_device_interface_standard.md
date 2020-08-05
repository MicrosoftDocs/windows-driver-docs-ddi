---
UID: NS:pcivirt._SRIOV_DEVICE_INTERFACE_STANDARD
title: _SRIOV_DEVICE_INTERFACE_STANDARD (pcivirt.h)
description: Stores function pointers to callback functions implemented by the physical function (PF) driver in the device stack for the of the SR-IOV device.
old-location: pci\sriov_device_interface_standard.htm
tech.root: PCI
ms.assetid: c71add7d-9920-4b2f-a46a-4a09a94f3900
ms.date: 02/24/2018
keywords: ["SRIOV_DEVICE_INTERFACE_STANDARD structure"]
ms.keywords: "*PSRIOV_DEVICE_INTERFACE_STANDARD, PCI.sriov_device_interface_standard, SRIOV_DEVICE_INTERFACE_STANDARD, SRIOV_DEVICE_INTERFACE_STANDARD structure [Buses], _SRIOV_DEVICE_INTERFACE_STANDARD, pcivirt/SRIOV_DEVICE_INTERFACE_STANDARD"
f1_keywords:
 - "pcivirt/SRIOV_DEVICE_INTERFACE_STANDARD"
 - "SRIOV_DEVICE_INTERFACE_STANDARD"
req.header: pcivirt.h
req.include-header:
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- SRIOV_DEVICE_INTERFACE_STANDARD
targetos: Windows
req.typenames: SRIOV_DEVICE_INTERFACE_STANDARD, *PSRIOV_DEVICE_INTERFACE_STANDARD
---

# _SRIOV_DEVICE_INTERFACE_STANDARD structure


## -description


Stores function pointers to callback functions implemented by the physical function (PF) driver  in the device stack for the of the SR-IOV device.


## -syntax


```cpp
typedef struct _SRIOV_DEVICE_INTERFACE_STANDARD {
  USHORT                           Size;
  USHORT                           Version;
  PVOID                            Context;
  PINTERFACE_REFERENCE             InterfaceReference;
  PINTERFACE_REFERENCE             InterfaceDereference;
  PSRIOV_READ_CONFIG               ReadVfConfig;
  PSRIOV_WRITE_CONFIG              WriteVfConfig;
  PSRIOV_READ_BLOCK                ReadVfConfigBlock;
  PSRIOV_WRITE_BLOCK               WriteVfConfigBlock;
  PSRIOV_QUERY_PROBED_BARS         QueryProbedBars;
  PSRIOV_GET_VENDOR_AND_DEVICE_IDS GetVendorAndDevice;
  PSRIOV_GET_DEVICE_LOCATION       GetDeviceLocation;
  PSRIOV_RESET_FUNCTION            ResetVf;
  PSRIOV_SET_POWER_STATE           SetVfPowerState;
  PSRIOV_GET_RESOURCE_FOR_BAR      GetResourceForBar;
  PSRIOV_QUERY_LUID                QueryLuid;
} SRIOV_DEVICE_INTERFACE_STANDARD, SRIOV_DEVICE_INTERFACE_STANDARD;
```


## -struct-fields




### -field Size

Size of this structure.


### -field Version

Version of this structure


### -field Context

Driver-defined context passed by the driver.


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>.


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>.


### -field ReadVfConfig

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_read_config">SRIOV_READ_CONFIG</a> callback function that serves as a handler for reading the VF’s configurations space from the non-privileged VM.


### -field WriteVfConfig

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_write_config">SRIOV_WRITE_CONFIG</a> callback function that serves as a handler for writing the VF’s configuration space from the non-privileged VM.


### -field ReadVfConfigBlock

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_read_block">SRIOV_READ_BLOCK</a> callback function that serves as a handler for reading blocks of configuration data from the non-privileged VM.


### -field WriteVfConfigBlock

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_write_block">SRIOV_WRITE_BLOCK</a> callback function that serves as a handler for writing blocks of configuration data from the non-privileged VM..


### -field QueryProbedBars

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_query_probed_bars">SRIOV_QUERY_PROBED_BARS</a> callback function that allows a non-privileged VM to determine the value of the VF’s Base Address Registers if the value of -1 previously is written.


### -field GetVendorAndDevice

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_get_vendor_and_device_ids">SRIOV_GET_VENDOR_AND_DEVICE_IDS</a> callback function that supplies the values from which the Plug and Play IDs for device is derived.


### -field GetDeviceLocation

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_get_device_location">SRIOV_GET_DEVICE_LOCATION</a> callback function that allows the a non-privileged VM to determine the bus to which the device is attached.


### -field ResetVf

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_reset_function">SRIOV_RESET_FUNCTION</a> callback function that causes the VF to be reset.


### -field SetVfPowerState

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_set_power_state">SRIOV_SET_POWER_STATE</a> callback function that serves as a handle for changing the device’s power state from the non-privileged VM.


### -field GetResourceForBar

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_get_resource_for_bar">SRIOV_GET_RESOURCE_FOR_BAR</a> callback function that gets the translated resource for a specific BAR.


### -field QueryLuid

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-sriov_query_luid">SRIOV_QUERY_LUID</a> callback function that gets the unique identifier of the VF.


## -see-also

<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>



<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdf_query_interface_config_init.md">WDF_QUERY_INTERFACE_CONFIG_INIT</a>



 

 


