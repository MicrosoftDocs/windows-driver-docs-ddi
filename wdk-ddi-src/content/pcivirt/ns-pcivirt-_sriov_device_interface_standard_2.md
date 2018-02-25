---
UID: NS:pcivirt._SRIOV_DEVICE_INTERFACE_STANDARD_2
title: "_SRIOV_DEVICE_INTERFACE_STANDARD_2"
author: windows-driver-content
description: Stores function pointers to callback functions implemented by the physical function (PF) driver in the device stack for the of the SR-IOV device. This is an extended version of SRIOV_DEVICE_INTERFACE_STANDARD.
old-location: pci\sriov_device_interface_standard_2.htm
old-project: PCI
ms.assetid: 46c9fa94-283c-481e-9fb1-2ed63df00386
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PSRIOV_DEVICE_INTERFACE_STANDARD_2, ,, 2, A, C, D, E, F, I, N, O, P, PCI.sriov_device_interface_standard_2, R, S, SRIOV_DEVICE_INTERFACE_STANDARD_2, SRIOV_DEVICE_INTERFACE_STANDARD_2 structure [Buses], T, V, _, _SRIOV_DEVICE_INTERFACE_STANDARD_2, pcivirt/SRIOV_DEVICE_INTERFACE_STANDARD_2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Pcivirt.h
apiname:
-	SRIOV_DEVICE_INTERFACE_STANDARD_2
product: Windows
targetos: Windows
req.typenames: SRIOV_DEVICE_INTERFACE_STANDARD_2, *PSRIOV_DEVICE_INTERFACE_STANDARD_2
---

# _SRIOV_DEVICE_INTERFACE_STANDARD_2 structure


## -description


Stores function pointers to callback functions implemented by the physical function (PF) driver  in the device stack for the of the SR-IOV device. This is an extended version of <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>. 


## -syntax


````
typedef struct _SRIOV_DEVICE_INTERFACE_STANDARD_2 {
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
  PSRIOV_QUERY_PROBED_BARS_2       QueryProbedBars_2;
  PSRIOV_QUERY_VF_LUID             QueryVfLuid;
  PSRIOV_QUERY_LUID_VF             QueryLuidVf;
} SRIOV_DEVICE_INTERFACE_STANDARD_2, SRIOV_DEVICE_INTERFACE_STANDARD_2;
````


## -struct-fields




### -field Size

Size of this structure.


### -field Version

Version of this structure


### -field Context

Driver-defined context passed by the driver.


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a>. 


### -field ReadVfConfig

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/0fef9d53-b8af-4c9b-9914-982bcfc26517">SRIOV_READ_CONFIG</a> callback function that serves as a handler for reading the VF’s configurations space from the non-privileged VM.


### -field WriteVfConfig

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/323c8150-ef58-42a4-8c8b-77081ecb64b3">SRIOV_WRITE_CONFIG</a> callback function that serves as a handler for writing the VF’s configuration space from the non-privileged VM.


### -field ReadVfConfigBlock

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/af0d3465-2854-47d9-a6a4-06f510229a59">SRIOV_READ_BLOCK</a> callback function that serves as a handler for reading blocks of configuration data from the non-privileged VM.


### -field WriteVfConfigBlock

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/da47d601-2fab-49bb-b669-909a2e5c95c0">SRIOV_WRITE_BLOCK</a> callback function that serves as a handler for writing blocks of configuration data from the non-privileged VM..


### -field QueryProbedBars

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/422a9212-7227-4508-8f06-0056349fa835">SRIOV_QUERY_PROBED_BARS</a> callback function that allows a non-privileged VM to determine the value of the VF’s Base Address Registers if the value of -1 previously is written.


### -field GetVendorAndDevice

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/d08bbaea-6f2b-49ef-bb8b-c1fe357e1c90">SRIOV_GET_VENDOR_AND_DEVICE_IDS</a> callback function that supplies the values from which the Plug and Play IDs for device is derived.


### -field GetDeviceLocation

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/705b52e3-f695-4c58-9ae2-5a806f1e2140">SRIOV_GET_DEVICE_LOCATION</a> callback function that allows the a non-privileged VM to determine the bus to which the device is attached.


### -field ResetVf

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/30c01528-8254-431f-aaba-79c05f66fc00">SRIOV_RESET_FUNCTION</a> callback function that causes the VF to be reset.


### -field SetVfPowerState

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/d43a21cb-5cee-4e72-8f0c-7aa8b2453507">SRIOV_SET_POWER_STATE</a> callback function that serves as a handle for changing the device’s power state from the non-privileged VM.


### -field GetResourceForBar

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/b52bafee-d541-4396-be0a-06956d07fb2b">SRIOV_GET_RESOURCE_FOR_BAR</a> callback function that gets the translated resource for a specific BAR.


### -field QueryLuid

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/9bb8e54f-b42a-4f61-a3f5-6972141c8f28">SRIOV_QUERY_LUID</a> callback function that gets the unique identifier of the VF.


### -field QueryProbedBars_2

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/e0c079aa-8adf-42c9-a4ac-bfc623471964">SRIOV_QUERY_PROBED_BARS_2</a> callback function.


### -field QueryVfLuid

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/17fe6e28-59ce-4678-8268-b49cef09a3db">SRIOV_QUERY_VF_LUID</a> callback function that gets the unique identifier of the VF.


### -field QueryLuidVf

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/00dddc92-08d1-4eaa-b3de-5e96c7a6d3e0">SRIOV_QUERY_LUID_VF</a> callback function that gets VF index for the specified unique identifier.

