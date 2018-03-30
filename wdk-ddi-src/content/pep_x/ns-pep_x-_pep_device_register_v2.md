---
UID: NS:pep_x._PEP_DEVICE_REGISTER_V2
title: "_PEP_DEVICE_REGISTER_V2"
author: windows-driver-content
description: The PEP_DEVICE_REGISTER structure describes all the components in a particular device.
old-location: kernel\pep_device_register_v2.htm
old-project: kernel
ms.assetid: 67747FF9-4808-45BB-8809-24B2CE56546B
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_DEVICE_REGISTER, *PPEP_DEVICE_REGISTER_V2, PEP_DEVICE_REGISTER, PEP_DEVICE_REGISTER_V2, PEP_DEVICE_REGISTER_V2 structure [Kernel-Mode Driver Architecture], PPEP_DEVICE_REGISTER_V2, PPEP_DEVICE_REGISTER_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_DEVICE_REGISTER_V2, kernel.pep_device_register_v2, pepfx/PEP_DEVICE_REGISTER_V2, pepfx/PPEP_DEVICE_REGISTER_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
topic_type:
-	kbSyntax
api_type:
-	<TBD>
api_location:
-
api_name:
-	PEP_DEVICE_REGISTER_V2
product: Windows
targetos: Windows
req.typenames: PEP_DEVICE_REGISTER_V2, *PPEP_DEVICE_REGISTER_V2, PEP_DEVICE_REGISTER_V2, *PPEP_DEVICE_REGISTER_V2
---

# _PEP_DEVICE_REGISTER_V2 structure


## -description


The <b>PEP_DEVICE_REGISTER</b> structure describes all the components in a particular device.


## -struct-fields




### -field Flags

TBD


### -field ComponentCount

The number of components in this device, which is also the number of elements in the <b>Components</b> array. The <b>ComponentCount</b> value must be greater than or equal to one.


### -field Components

The first element in an array of pointers to <a href="https://msdn.microsoft.com/library/windows/hardware/mt186705">PEP_COMPONENT_V2</a> structures. Each element in the array points to a structure that describes a component in the device. If this array contains more than one element, the additional elements immediately follow the end of the <b>PEP_DEVICE_REGISTER</b> structure.


## -remarks



The <a href="https://msdn.microsoft.com/A1363B34-CC5C-482E-8E8D-62D7263545E3">PEP_REGISTER_DEVICE</a> structure contains a <b>Register</b> member that points to a <b>PEP_DEVICE_REGISTER</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186705">PEP_COMPONENT_V2</a>



<a href="https://msdn.microsoft.com/A1363B34-CC5C-482E-8E8D-62D7263545E3">PEP_REGISTER_DEVICE</a>
 

 

