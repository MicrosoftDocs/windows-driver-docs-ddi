---
UID: NS:wdm._CM_PARTIAL_RESOURCE_LIST
title: _CM_PARTIAL_RESOURCE_LIST (wdm.h)
description: The CM_PARTIAL_RESOURCE_LIST structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a CM_FULL_RESOURCE_DESCRIPTOR structure.
old-location: kernel\cm_partial_resource_list.htm
tech.root: kernel
ms.assetid: f16b26f5-1f32-4c2e-83ec-0a0f79a4be85
ms.date: 04/30/2018
ms.keywords: "*PCM_PARTIAL_RESOURCE_LIST, CM_PARTIAL_RESOURCE_LIST, CM_PARTIAL_RESOURCE_LIST structure [Kernel-Mode Driver Architecture], PCM_PARTIAL_RESOURCE_LIST, PCM_PARTIAL_RESOURCE_LIST structure pointer [Kernel-Mode Driver Architecture], _CM_PARTIAL_RESOURCE_LIST, kernel.cm_partial_resource_list, kstruct_a_26d7ed25-e580-41e2-ae9d-5e06eb263e3d.xml, wdm/CM_PARTIAL_RESOURCE_LIST, wdm/PCM_PARTIAL_RESOURCE_LIST"
ms.topic: struct
req.header: wdm.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CM_PARTIAL_RESOURCE_LIST
product:
- Windows
targetos: Windows
req.typenames: CM_PARTIAL_RESOURCE_LIST, *PCM_PARTIAL_RESOURCE_LIST
---

# _CM_PARTIAL_RESOURCE_LIST structure


## -description


The <b>CM_PARTIAL_RESOURCE_LIST</b> structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541954">CM_FULL_RESOURCE_DESCRIPTOR</a> structure.


## -struct-fields




### -field Version

The version number of this structure. This value should be 1.


### -field Revision

The revision of this structure. This value should be 1.


### -field Count

The number of elements contained in the <b>PartialDescriptors</b> array.


### -field PartialDescriptors

The first element in an array of one or more <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structures.


## -remarks



This structure is the header for an array of <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structures. The <b>PartialDescriptors</b> member contains the first element in this array, and the <b>Count</b> member specifies the total number of array elements. If the array contains more than one element, the remaining elements in the array immediately follow the <b>CM_PARTIAL_RESOURCE_LIST</b> structure in memory. The total number of bytes occupied by the <b>CM_PARTIAL_RESOURCE_LIST</b> structure and any array elements that follow this structure is <b>sizeof</b>(<b>CM_PARTIAL_RESOURCE_LIST</b>) + (<b>Count</b> - 1) * <b>sizeof</b>(<b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b>).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541954">CM_FULL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
 

 

