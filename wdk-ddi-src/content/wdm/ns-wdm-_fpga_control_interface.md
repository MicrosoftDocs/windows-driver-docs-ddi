---
UID: NS:wdm._FPGA_CONTROL_INTERFACE
title: _FPGA_CONTROL_INTERFACE
author: windows-driver-content
description: Reserved for future use.
ms.assetid: e0dae56e-1f6c-4695-8168-58c1a5439e37
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _FPGA_CONTROL_INTERFACE, FPGA_CONTROL_INTERFACE, *PFPGA_CONTROL_INTERFACE, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: FPGA_CONTROL_INTERFACE, *PFPGA_CONTROL_INTERFACE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	_FPGA_CONTROL_INTERFACE
product:
-	Windows
targetos: Windows
---

# _FPGA_CONTROL_INTERFACE structure

## -description
Reserved for future use.

## -struct-fields

### -field Size
The size, in bytes, of this structure.
 
### -field Version
The driver-defined interface version. The current version of this interface is FPGA_CONTROL_INTERFACE_VERSION.
 
### -field Context
A pointer to interface-specific context information.
 
### -field InterfaceReference
A pointer to an [InterfaceReference](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfwdm/nc-wudfwdm-pinterface_reference) routine that increments the interface's reference count.
 
### -field InterfaceDereference
A pointer to an [InterfaceDereference](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfwdm/nc-wudfwdm-pinterface_dereference) routine that decrements the interface's reference count.
 
### -field BusScan
A pointer to a [_FPGA_BUS_SCAN_](nc-wdm-fpga_bus_scan.md) callback function that triggers a bus scan at the parent of the FPGA device.
 
### -field ControlLink
A pointer to a [_FPGA_CONTROL_LINK_](nc-wdm-fpga_control_link.md) callback function that enables or disables the link between the given FPGA device and its parent bridge.
 
### -field ControlConfigSpace
A pointer to a [_FPGA_CONTROL_CONFIG_SPACE_](nc-wdm-fpga_control_config_space.md) callback function that enables or disables the access to the configuration space of the FPGA device.  
 
### -field ControlErrorReporting
A pointer to a [_FPGA_CONTROL_ERROR_REPORTING_](nc-wdm-fpga_control_error_reporting.md) callback function that toggles the error reporting for the FPGA device and its parent bridge. 

## -remarks
A device driver that successfully queries for the GUID_PCI_FPGA_CONTROL_INTERFACE interface receives a pointer to a [**_FPGA_CONTROL_INTERFACE**] structure in which the pointers to the routines in the interface are all non-NULL and valid. 

The [**_FPGA_CONTROL_INTERFACE**] structure is an extended version of the [INTERFACE] structure.

## -see-also
