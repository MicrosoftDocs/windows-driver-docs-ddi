---
UID: NE:ucxcontroller._UCX_CONTROLLER_PARENT_BUS_TYPE
title: "_UCX_CONTROLLER_PARENT_BUS_TYPE"
author: windows-driver-content
description: The UCX_CONTROLLER_PARENT_BUS_TYPE enumeration defines the parent bus type.
old-location: buses\ucx_controller_parent_bus_type.htm
old-project: usbref
ms.assetid: FD78074D-E128-4085-A178-0133C9256E42
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCX_CONTROLLER_PARENT_BUS_TYPE, UCX_CONTROLLER_PARENT_BUS_TYPE enumeration [Buses], UcxControllerParentBusTypeAcpi, UcxControllerParentBusTypeCustom, UcxControllerParentBusTypePci, _UCX_CONTROLLER_PARENT_BUS_TYPE, buses.ucx_controller_parent_bus_type, ucxcontroller/UCX_CONTROLLER_PARENT_BUS_TYPE, ucxcontroller/UcxControllerParentBusTypeAcpi, ucxcontroller/UcxControllerParentBusTypeCustom, ucxcontroller/UcxControllerParentBusTypePci
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucxcontroller.h
apiname:
-	UCX_CONTROLLER_PARENT_BUS_TYPE
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_PARENT_BUS_TYPE
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_PARENT_BUS_TYPE enumeration


## -description


The <b>UCX_CONTROLLER_PARENT_BUS_TYPE</b> enumeration defines the parent bus type.


## -syntax


````
typedef enum _UCX_CONTROLLER_PARENT_BUS_TYPE { 
  UcxControllerParentBusTypeCustom,
  UcxControllerParentBusTypePci,
  UcxControllerParentBusTypeAcpi
} UCX_CONTROLLER_PARENT_BUS_TYPE;
````


## -enum-fields




### -field UcxControllerParentBusTypeCustom

Custom bus type.


### -field UcxControllerParentBusTypePci

Parent bus is PCI.


### -field UcxControllerParentBusTypeAcpi

Parent is ACPI.


### -field UcxControllerParentBusTypeMaUsb




## -see-also

<a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_config.md">UCX_CONTROLLER_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_CONTROLLER_PARENT_BUS_TYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

