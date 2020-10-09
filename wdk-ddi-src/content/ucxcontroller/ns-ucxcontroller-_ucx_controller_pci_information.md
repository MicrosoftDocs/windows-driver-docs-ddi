---
UID: NS:ucxcontroller._UCX_CONTROLLER_PCI_INFORMATION
title: _UCX_CONTROLLER_PCI_INFORMATION (ucxcontroller.h)
description: This structure provides information about a PCI USB controller.
old-location: buses\_ucx_controller_pci_information.htm
tech.root: usbref
ms.assetid: 178C9423-D7C9-43FD-BC80-A675383BDE9B
ms.date: 05/07/2018
keywords: ["UCX_CONTROLLER_PCI_INFORMATION structure"]
ms.keywords: "*PUCX_CONTROLLER_PCI_INFORMATION, P_UCX_CONTROLLER_PCI_INFORMATION, P_UCX_CONTROLLER_PCI_INFORMATION structure pointer [Buses], UCX_CONTROLLER_PCI_INFORMATION, UCX_CONTROLLER_PCI_INFORMATION structure [Buses], _UCX_CONTROLLER_PCI_INFORMATION, buses._ucx_controller_pci_information, ucxcontroller/P_UCX_CONTROLLER_PCI_INFORMATION, ucxcontroller/_UCX_CONTROLLER_PCI_INFORMATION"
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
req.typenames: UCX_CONTROLLER_PCI_INFORMATION, *PUCX_CONTROLLER_PCI_INFORMATION
f1_keywords:
 - _UCX_CONTROLLER_PCI_INFORMATION
 - ucxcontroller/_UCX_CONTROLLER_PCI_INFORMATION
 - PUCX_CONTROLLER_PCI_INFORMATION
 - ucxcontroller/PUCX_CONTROLLER_PCI_INFORMATION
 - UCX_CONTROLLER_PCI_INFORMATION
 - ucxcontroller/UCX_CONTROLLER_PCI_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucxcontroller.h
api_name:
 - UCX_CONTROLLER_PCI_INFORMATION
---

# _UCX_CONTROLLER_PCI_INFORMATION structure


## -description

This structure provides information about a PCI USB controller.

## -struct-fields

### -field VendorId

The vendor ID for the PCI USB controller.

### -field DeviceId

The device ID for the PCI USB controller.

### -field RevisionId

The revision ID for the PCI USB controller.

### -field BusNumber

Specifies the bus number that identifies the bus instance that a device instance is attached to.

### -field DeviceNumber

Specifies the device number that is assigned to the logical PCI slot.

### -field FunctionNumber

Specifies the specific function on the device that is located in the logical PCI slot.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_config">UCX_CONTROLLER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucx_controller_config_set_pci_info">UCX_CONTROLLER_CONFIG_SET_PCI_INFO</a>



<a href="/windows-hardware/drivers/ddi/ucxcontroller/ne-ucxcontroller-_ucx_controller_parent_bus_type">UCX_CONTROLLER_PARENT_BUS_TYPE</a>