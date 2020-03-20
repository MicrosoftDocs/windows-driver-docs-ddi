---
UID: NF:ucxcontroller.UCX_CONTROLLER_CONFIG_SET_ACPI_INFO
title: UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function (ucxcontroller.h)
description: Initializes a UCX_CONTROLLER_CONFIG structure with the specified values for the controller with ACPI as the parent.
old-location: buses\_ucx_controller_config_set_acpi_info.htm
tech.root: usbref
ms.assetid: D060CE9D-B23A-4E6C-9CC3-1DDAB0583FF8
ms.date: 05/07/2018
keywords: ["UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function"]
ms.keywords: UCX_CONTROLLER_CONFIG_SET_ACPI_INFO, UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function [Buses], buses._ucx_controller_config_set_acpi_info, ucxcontroller/UCX_CONTROLLER_CONFIG_SET_ACPI_INFO
f1_keywords:
 - "ucxcontroller/UCX_CONTROLLER_CONFIG_SET_ACPI_INFO"
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ucxcontroller.h
api_name:
- UCX_CONTROLLER_CONFIG_SET_ACPI_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function


## -description


Initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_config">UCX_CONTROLLER_CONFIG</a> structure with the specified values for the controller with ACPI as the parent. 


## -parameters




### -param Config

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_config">UCX_CONTROLLER_CONFIG</a> structure to initialize.


### -param VendorId

A string that contains the vendor identifier for the device.


### -param DeviceId

A string that specifies the device identifier assigned by the manufacturer.


### -param RevisionId

A string that Specifies the revision level of the device described by the <b>DeviceID</b> member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxcontroller/ns-ucxcontroller-_ucx_controller_config">UCX_CONTROLLER_CONFIG</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>
 

 

