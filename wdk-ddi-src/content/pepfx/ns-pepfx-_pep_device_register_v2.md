---
UID: NS:pepfx._PEP_DEVICE_REGISTER_V2
title: "_PEP_DEVICE_REGISTER_V2"
author: windows-driver-content
description: The PEP_DEVICE_REGISTER structure describes all the components in a particular device.
old-location: kernel\pep_device_register_v2.htm
old-project: kernel
ms.assetid: 67747FF9-4808-45BB-8809-24B2CE56546B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_DEVICE_REGISTER_V2 structure [Kernel-Mode Driver Architecture], pepfx/PPEP_DEVICE_REGISTER_V2, *PPEP_DEVICE_REGISTER, PEP_DEVICE_REGISTER, PEP_DEVICE_REGISTER_V2, *PPEP_DEVICE_REGISTER_V2, kernel.pep_device_register_v2, PPEP_DEVICE_REGISTER_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_DEVICE_REGISTER_V2, PPEP_DEVICE_REGISTER_V2, pepfx/PEP_DEVICE_REGISTER_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
topictype:
-	kbSyntax
apitype:
-	<TBD>
apilocation:
-
apiname:
-	PEP_DEVICE_REGISTER_V2
product: Windows
targetos: Windows
req.typenames: "*PPEP_DEVICE_REGISTER_V2, PEP_DEVICE_REGISTER_V2"
---

# _PEP_DEVICE_REGISTER_V2 structure


## -description


The <b>PEP_DEVICE_REGISTER</b> structure describes all the components in a particular device.


## -syntax


````
typedef struct _PEP_DEVICE_REGISTER_V2 {
  ULONGLONG         Flags;
  ULONG             ComponentCount;
  PPEP_COMPONENT_V2 Components[ANYSIZE_ARRAY];
} PEP_DEVICE_REGISTER_V2, *PPEP_DEVICE_REGISTER_V2;
````


## -struct-fields




### -field Flags

TBD


### -field ComponentCount

The number of components in this device, which is also the number of elements in the <b>Components</b> array. The <b>ComponentCount</b> value must be greater than or equal to one.


### -field Components

The first element in an array of pointers to <a href="..\pepfx\ns-pepfx-_pep_component_v2.md">PEP_COMPONENT_V2</a> structures. Each element in the array points to a structure that describes a component in the device. If this array contains more than one element, the additional elements immediately follow the end of the <b>PEP_DEVICE_REGISTER</b> structure.


## -remarks


The <a href="..\pepfx\ns-pepfx-_pep_register_device_v2.md">PEP_REGISTER_DEVICE</a> structure contains a <b>Register</b> member that points to a <b>PEP_DEVICE_REGISTER</b> structure.



## -see-also

<a href="..\pepfx\ns-pepfx-_pep_component_v2.md">PEP_COMPONENT_V2</a>

<a href="..\pepfx\ns-pepfx-_pep_register_device_v2.md">PEP_REGISTER_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_DEVICE_REGISTER_V2 structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

