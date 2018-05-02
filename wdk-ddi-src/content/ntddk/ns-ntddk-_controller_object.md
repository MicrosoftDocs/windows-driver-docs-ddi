---
UID: NS:ntddk._CONTROLLER_OBJECT
title: "_CONTROLLER_OBJECT"
author: windows-driver-content
description: A controller object represents a hardware adapter or controller with homogenous devices that are the actual targets for I/O requests.
old-location: kernel\controller_object.htm
old-project: kernel
ms.assetid: a5530901-e48c-4f4e-86a8-00d5ed01f933
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PCONTROLLER_OBJECT, CONTROLLER_OBJECT, CONTROLLER_OBJECT structure [Kernel-Mode Driver Architecture], PCONTROLLER_OBJECT, PCONTROLLER_OBJECT structure pointer [Kernel-Mode Driver Architecture], _CONTROLLER_OBJECT, kernel.controller_object, kstruct_a_391d0fc2-3a61-4b2b-b571-143d2af7ef9b.xml, ntddk/CONTROLLER_OBJECT, ntddk/PCONTROLLER_OBJECT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	Ntddk.h
api_name:
-	CONTROLLER_OBJECT
product:
- Windows
targetos: Windows
req.typenames: CONTROLLER_OBJECT, *PCONTROLLER_OBJECT
---

# _CONTROLLER_OBJECT structure


## -description


A controller object represents a hardware adapter or controller with homogenous devices that are the actual targets for I/O requests. A controller object can be used to synchronize a device driver's I/O to the target devices through its hardware adapter/controller. 

A controller object is partially opaque. Driver writers must know about a certain field associated with the controller object because their drivers access this field through the controller object pointer returned by <b>IoCreateController</b>. The following field in a controller object is accessible to the creating driver. 


## -struct-fields




### -field Type

 


### -field Size

 


### -field ControllerExtension

Pointer to the controller extension. The structure and contents of the controller extension are driver-defined. The size is driver-determined, specified in the driver's call to <b>IoCreateController</b>. Usually, drivers maintain common state about I/O operations in the controller extension and device-specific state about I/O for a target device in the corresponding device extension. 


### -field DeviceWaitQueue

 


### -field Spare1

 


### -field Spare2

 




## -remarks



Most driver routines that process IRPs are given a pointer to the target device object. Consequently, device drivers that use controller objects frequently store the controller object pointer returned by <b>IoCreateController</b> in each device extension. 

Note that a controller object has no name so it cannot be the target of an I/O request, and higher-level drivers cannot connect or attach their device objects to a device driver's controller object. 

Undocumented fields within a controller object should be considered inaccessible. Drivers with dependencies on object field locations or access to undocumented fields might not remain portable and interoperable with other drivers over time.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548395">IoCreateController</a>
 

 

