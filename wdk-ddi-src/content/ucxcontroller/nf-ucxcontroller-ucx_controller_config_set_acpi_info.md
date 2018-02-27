---
UID: NF:ucxcontroller.UCX_CONTROLLER_CONFIG_SET_ACPI_INFO
title: UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function
author: windows-driver-content
description: Initializes a UCX_CONTROLLER_CONFIG structure with the specified values for the controller with ACPI as the parent.
old-location: buses\_ucx_controller_config_set_acpi_info.htm
old-project: usbref
ms.assetid: D060CE9D-B23A-4E6C-9CC3-1DDAB0583FF8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCX_CONTROLLER_CONFIG_SET_ACPI_INFO, UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function [Buses], buses._ucx_controller_config_set_acpi_info, ucxcontroller/UCX_CONTROLLER_CONFIG_SET_ACPI_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
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
-	UCX_CONTROLLER_CONFIG_SET_ACPI_INFO
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function


## -description


Initializes a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a> structure with the specified values for the controller with ACPI as the parent. 


## -syntax


````
__inline
void UCX_CONTROLLER_CONFIG_SET_ACPI_INFO(
   PUCX_CONTROLLER_CONFIG Config,
   PSTR                   VendorId,
   PSTR                   DeviceId,
   PSTR                   RevisionId
);
````


## -parameters




### -param Config

A pointer to a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a> structure to initialize.


### -param VendorId

A string that contains the vendor identifier for the device.


### -param DeviceId

A string that specifies the device identifier assigned by the manufacturer.


### -param RevisionId

A string that Specifies the revision level of the device described by the <b>DeviceID</b> member.


## -returns



This function does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>



<a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_CONTROLLER_CONFIG_SET_ACPI_INFO function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

