---
UID: NS:wdm._CM_PARTIAL_RESOURCE_LIST
title: CM_PARTIAL_RESOURCE_LIST (wdm.h)
description: The CM_PARTIAL_RESOURCE_LIST structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a CM_FULL_RESOURCE_DESCRIPTOR structure.
tech.root: kernel
ms.date: 01/06/2023
keywords: ["CM_PARTIAL_RESOURCE_LIST structure"]
ms.keywords: "*PCM_PARTIAL_RESOURCE_LIST, CM_PARTIAL_RESOURCE_LIST, CM_PARTIAL_RESOURCE_LIST structure [Kernel-Mode Driver Architecture], PCM_PARTIAL_RESOURCE_LIST, PCM_PARTIAL_RESOURCE_LIST structure pointer [Kernel-Mode Driver Architecture], _CM_PARTIAL_RESOURCE_LIST, kernel.cm_partial_resource_list, kstruct_a_26d7ed25-e580-41e2-ae9d-5e06eb263e3d.xml, wdm/CM_PARTIAL_RESOURCE_LIST, wdm/PCM_PARTIAL_RESOURCE_LIST"
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
targetos: Windows
req.typenames: CM_PARTIAL_RESOURCE_LIST, *PCM_PARTIAL_RESOURCE_LIST
f1_keywords:
 - _CM_PARTIAL_RESOURCE_LIST
 - wdm/_CM_PARTIAL_RESOURCE_LIST
 - PCM_PARTIAL_RESOURCE_LIST
 - wdm/PCM_PARTIAL_RESOURCE_LIST
 - CM_PARTIAL_RESOURCE_LIST
 - wdm/CM_PARTIAL_RESOURCE_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _CM_PARTIAL_RESOURCE_LIST
 - PCM_PARTIAL_RESOURCE_LIST
 - CM_PARTIAL_RESOURCE_LIST
---

## -description

The **CM_PARTIAL_RESOURCE_LIST** structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a [CM_FULL_RESOURCE_DESCRIPTOR](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor) structure.

## -struct-fields

### -field Version

The version number of this structure. This value should be 1.

### -field Revision

The revision of this structure. This value should be 1.

### -field Count

The number of elements contained in the **PartialDescriptors** array.

### -field PartialDescriptors

The first element in an array of one or more [CM_PARTIAL_RESOURCE_DESCRIPTOR](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor) structures.

## -remarks

This structure is the header for an array of **CM_PARTIAL_RESOURCE_DESCRIPTOR** structures. The **PartialDescriptors** member contains the first element in this array, and the **Count** member specifies the total number of array elements. If the array contains more than one element, the remaining elements in the array immediately follow the **CM_PARTIAL_RESOURCE_LIST** structure in memory. The total number of bytes occupied by the **CM_PARTIAL_RESOURCE_LIST** structure and any array elements that follow this structure is **sizeof**(**CM_PARTIAL_RESOURCE_LIST**) + (**Count** - 1) * **sizeof**(**CM_PARTIAL_RESOURCE_DESCRIPTOR**).

If the last **CM_PARTIAL_RESOURCE_DESCRIPTOR** in the **CM_PARTIAL_RESOURCE_LIST** has a Type of **CmResourceTypeDeviceSpecific**, then you need to add the size of the device specific data block to the total above.

## -see-also

[CM_FULL_RESOURCE_DESCRIPTOR](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor)

[CM_PARTIAL_RESOURCE_DESCRIPTOR](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor)
