---
UID: NF:ucxcontroller.UCX_CONTROLLER_CONFIG_SET_PCI_INFO
title: UCX_CONTROLLER_CONFIG_SET_PCI_INFO function
author: windows-driver-content
description: Initializes a UCX_CONTROLLER_CONFIG structure with the specified values for the controller with PCI as the parent bus type.
old-location: buses\_ucx_controller_config_set_pci_info.htm
old-project: usbref
ms.assetid: 493B8E5B-D2CC-453E-8202-69337FAC85ED
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucxcontroller/UCX_CONTROLLER_CONFIG_SET_PCI_INFO, buses._ucx_controller_config_set_pci_info, UCX_CONTROLLER_CONFIG_SET_PCI_INFO function [Buses], UCX_CONTROLLER_CONFIG_SET_PCI_INFO
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ucxcontroller.h
apiname: 
-	UCX_CONTROLLER_CONFIG_SET_PCI_INFO
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UCX_CONTROLLER_CONFIG_SET_PCI_INFO function


## -description


Initializes a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a> structure with the specified values for the controller with PCI as the parent bus type.


## -syntax


````
__inline
void UCX_CONTROLLER_CONFIG_SET_PCI_INFO(
  _In_ PUCX_CONTROLLER_CONFIG Config,
  _In_ ULONG                  VendorId,
  _In_ ULONG                  DeviceId,
  _In_ USHORT                 RevisionId,
  _In_ ULONG                  BusNumber,
  _In_ ULONG                  DeviceNumber,
  _In_ ULONG                  FunctionNumber
);
````


## -parameters




### -param Config [in]

A pointer to a <a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a> structure to initialize.


### -param VendorId [in]

Specifies the vendor identifier for the device as assigned by the PCI SIG.


### -param DeviceId [in]

Specifies the device identifier assigned by the manufacturer. 


### -param RevisionId [in]

Specifies the revision level of the device described by the <b>DeviceID</b> member.


### -param BusNumber [in]

Specifies the bus number that identifies the bus instance that a device instance is attached to.


### -param DeviceNumber [in]

Specifies the device number that is assigned to the logical PCI slot. 


### -param FunctionNumber [in]

Specifies the specific function on the device that is located in the logical PCI slot. 


## -returns


This function does not return a value.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>

<a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_CONTROLLER_CONFIG_SET_PCI_INFO function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

