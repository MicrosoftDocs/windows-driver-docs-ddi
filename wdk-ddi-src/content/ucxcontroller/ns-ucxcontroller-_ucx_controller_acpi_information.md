---
UID: NS:ucxcontroller._UCX_CONTROLLER_ACPI_INFORMATION
title: "_UCX_CONTROLLER_ACPI_INFORMATION"
author: windows-driver-content
description: This structure provides information about an advanced Configuration and power interface (ACPI) USB controller.
old-location: buses\_ucx_controller_acpi_information.htm
old-project: usbref
ms.assetid: BB5C69FF-166A-4A38-BF5E-FD644FCD1285
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_CONTROLLER_ACPI_INFORMATION, P_UCX_CONTROLLER_ACPI_INFORMATION, P_UCX_CONTROLLER_ACPI_INFORMATION structure pointer [Buses], UCX_CONTROLLER_ACPI_INFORMATION, UCX_CONTROLLER_ACPI_INFORMATION structure [Buses], _UCX_CONTROLLER_ACPI_INFORMATION, buses._ucx_controller_acpi_information, ucxcontroller/P_UCX_CONTROLLER_ACPI_INFORMATION, ucxcontroller/_UCX_CONTROLLER_ACPI_INFORMATION"
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
-	UCX_CONTROLLER_ACPI_INFORMATION
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_ACPI_INFORMATION, *PUCX_CONTROLLER_ACPI_INFORMATION
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_ACPI_INFORMATION structure


## -description


This structure provides information about an advanced Configuration and power interface (ACPI) USB controller.


## -syntax


````
typedef struct _UCX_CONTROLLER_ACPI_INFORMATION {
  CHAR VendorId[MAX_VENDOR_ID_STRING_LENGTH];
  CHAR DeviceId[MAX_DEVICE_ID_STRING_LENGTH];
  CHAR RevisionId[MAX_REVISION_ID_STRING_LENGTH];
} UCX_CONTROLLER_ACPI_INFORMATION, *P_UCX_CONTROLLER_ACPI_INFORMATION;
````


## -struct-fields




### -field VendorId

The vendor ID of the ACPI USB controller.


### -field DeviceId

The device ID of the ACPI USB controller.


### -field RevisionId

The revision ID of the ACPI USB controller.


## -see-also

<a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a>



<a href="..\ucxcontroller\nf-ucxcontroller-ucx_controller_config_set_acpi_info.md">UCX_CONTROLLER_CONFIG_SET_ACPI_INFO</a>



 

 


