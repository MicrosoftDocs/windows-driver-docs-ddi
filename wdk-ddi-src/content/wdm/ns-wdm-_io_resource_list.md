---
UID: NS:wdm._IO_RESOURCE_LIST
title: _IO_RESOURCE_LIST (wdm.h)
description: The _IO_RESOURCE_LIST structure (wdm.h) describes a range of raw hardware resources, of various types, that can be used by a device.
old-location: kernel\io_resource_list.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IO_RESOURCE_LIST structure"]
ms.keywords: "*PIO_RESOURCE_LIST, IO_RESOURCE_LIST, IO_RESOURCE_LIST structure [Kernel-Mode Driver Architecture], PIO_RESOURCE_LIST, PIO_RESOURCE_LIST structure pointer [Kernel-Mode Driver Architecture], _IO_RESOURCE_LIST, kernel.io_resource_list, kstruct_b_2e2d049f-a7c9-4051-8fa7-639bf03b5aae.xml, wdm/IO_RESOURCE_LIST, wdm/PIO_RESOURCE_LIST"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.typenames: IO_RESOURCE_LIST, *PIO_RESOURCE_LIST
f1_keywords:
 - _IO_RESOURCE_LIST
 - wdm/_IO_RESOURCE_LIST
 - PIO_RESOURCE_LIST
 - wdm/PIO_RESOURCE_LIST
 - IO_RESOURCE_LIST
 - wdm/IO_RESOURCE_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _IO_RESOURCE_LIST
 - PIO_RESOURCE_LIST
 - IO_RESOURCE_LIST
---

# _IO_RESOURCE_LIST structure (wdm.h)


## -description

The <b>IO_RESOURCE_LIST</b> structure describes a range of raw hardware resources, of various types, that can be used by a device. The resources specified represent a single, acceptable resource configuration for a device. An array of <b>IO_RESOURCE_LIST</b> structures is contained within each <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_requirements_list">IO_RESOURCE_REQUIREMENTS_LIST</a> structure.

## -struct-fields

### -field Version

The version number of this structure. This value should be 1.

### -field Revision

The revision of this structure. This value should be 1.

### -field Count

The number of elements in the <b>Descriptors</b> array.

### -field Descriptors

The first element in an array of one or more <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structures.

## -remarks

This structure is the header for an array of <b>IO_RESOURCE_DESCRIPTOR</b> structures. The <b>Descriptors</b> member contains the first element in this array, and the <b>Count</b> member specifies the total number of array elements. If the array contains more than one element, the remaining elements in the array immediately follow the <b>IO_RESOURCE_LIST</b> structure in memory. The total number of bytes occupied by the <b>IO_RESOURCE_LIST</b> structure and any array elements that follow this structure is <b>sizeof</b>(<b>IO_RESOURCE_LIST</b>) + (<b>Count</b> - 1) * <b>sizeof</b>(<b>IO_RESOURCE_DESCRIPTOR</b>).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_requirements_list">IO_RESOURCE_REQUIREMENTS_LIST</a>

