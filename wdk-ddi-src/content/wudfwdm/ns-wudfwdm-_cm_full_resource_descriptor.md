---
UID: NS:wudfwdm._CM_FULL_RESOURCE_DESCRIPTOR
title: "_CM_FULL_RESOURCE_DESCRIPTOR"
author: windows-driver-content
description: The CM_FULL_RESOURCE_DESCRIPTOR structure specifies a set of system hardware resources of various types, assigned to a device that is connected to a specific bus. This structure is contained within a CM_RESOURCE_LIST structure.
old-location: kernel\cm_full_resource_descriptor.htm
old-project: kernel
ms.assetid: e405c545-da0c-4b47-84c2-dd26d746da94
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PCM_FULL_RESOURCE_DESCRIPTOR, CM_FULL_RESOURCE_DESCRIPTOR, CM_FULL_RESOURCE_DESCRIPTOR structure [Kernel-Mode Driver Architecture], PCM_FULL_RESOURCE_DESCRIPTOR, PCM_FULL_RESOURCE_DESCRIPTOR structure pointer [Kernel-Mode Driver Architecture], _CM_FULL_RESOURCE_DESCRIPTOR, kernel.cm_full_resource_descriptor, kstruct_a_eb7de4ac-cd02-44cc-9e26-a9c2a99eb8e6.xml, wdm/CM_FULL_RESOURCE_DESCRIPTOR, wdm/PCM_FULL_RESOURCE_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CM_FULL_RESOURCE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: CM_FULL_RESOURCE_DESCRIPTOR, *PCM_FULL_RESOURCE_DESCRIPTOR
req.product: Windows 10 or later.
---

# _CM_FULL_RESOURCE_DESCRIPTOR structure


## -description


The <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure specifies a set of system hardware resources of various types, assigned to a device that is connected to a specific bus. This structure is contained within a <a href="..\wudfwdm\ns-wudfwdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure.


## -syntax


````
typedef struct _CM_FULL_RESOURCE_DESCRIPTOR {
  INTERFACE_TYPE           InterfaceType;
  ULONG                    BusNumber;
  CM_PARTIAL_RESOURCE_LIST PartialResourceList;
} CM_FULL_RESOURCE_DESCRIPTOR, *PCM_FULL_RESOURCE_DESCRIPTOR;
````


## -struct-fields




### -field InterfaceType

Specifies the type of bus to which the device is connected. This must be one of the types defined by <a href="..\wudfwdm\ne-wudfwdm-_interface_type.md">INTERFACE_TYPE</a>, in Wdm.h or Ntddk.h. (Not used by WDM drivers.)


### -field BusNumber

The system-assigned, driver-supplied, zero-based number of the bus to which the device is connected. (Not used by WDM drivers.)  


### -field PartialResourceList

A <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_list.md">CM_PARTIAL_RESOURCE_LIST</a> structure. 


## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_list.md">CM_PARTIAL_RESOURCE_LIST</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>



 

 



