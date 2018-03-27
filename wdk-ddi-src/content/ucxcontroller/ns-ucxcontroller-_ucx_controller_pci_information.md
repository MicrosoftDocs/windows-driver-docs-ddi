---
UID: NS:ucxcontroller._UCX_CONTROLLER_PCI_INFORMATION
title: "_UCX_CONTROLLER_PCI_INFORMATION"
author: windows-driver-content
description: This structure provides information about a PCI USB controller.
old-location: buses\_ucx_controller_pci_information.htm
old-project: usbref
ms.assetid: 178C9423-D7C9-43FD-BC80-A675383BDE9B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_CONTROLLER_PCI_INFORMATION, P_UCX_CONTROLLER_PCI_INFORMATION, P_UCX_CONTROLLER_PCI_INFORMATION structure pointer [Buses], UCX_CONTROLLER_PCI_INFORMATION, UCX_CONTROLLER_PCI_INFORMATION structure [Buses], _UCX_CONTROLLER_PCI_INFORMATION, buses._ucx_controller_pci_information, ucxcontroller/P_UCX_CONTROLLER_PCI_INFORMATION, ucxcontroller/_UCX_CONTROLLER_PCI_INFORMATION"
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
-	UCX_CONTROLLER_PCI_INFORMATION
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_PCI_INFORMATION, *PUCX_CONTROLLER_PCI_INFORMATION
req.product: Windows 10 or later.
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




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188057">UCX_CONTROLLER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188059">UCX_CONTROLLER_CONFIG_SET_PCI_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187948">UCX_CONTROLLER_PARENT_BUS_TYPE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_CONTROLLER_PCI_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

