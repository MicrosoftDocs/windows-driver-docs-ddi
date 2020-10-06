---
UID: NE:wdfmemory._WDF_MEMORY_DESCRIPTOR_TYPE
title: _WDF_MEMORY_DESCRIPTOR_TYPE (wdfmemory.h)
description: The WDF_MEMORY_DESCRIPTOR_TYPE enumeration identifies the types of memory descriptions that a WDF_MEMORY_DESCRIPTOR structure can specify.
old-location: wdf\wdf_memory_descriptor_type.htm
tech.root: wdf
ms.assetid: ab364ad8-1b04-4ad0-a036-9b1c41e16604
ms.date: 02/26/2018
keywords: ["WDF_MEMORY_DESCRIPTOR_TYPE enumeration"]
ms.keywords: DFMemoryObjectRef_3817f18e-3d20-43d6-b6f0-584c1533fe9a.xml, WDF_MEMORY_DESCRIPTOR_TYPE, WDF_MEMORY_DESCRIPTOR_TYPE enumeration, WdfMemoryDescriptorTypeBuffer, WdfMemoryDescriptorTypeHandle, WdfMemoryDescriptorTypeInvalid, WdfMemoryDescriptorTypeMdl, _WDF_MEMORY_DESCRIPTOR_TYPE, kmdf.wdf_memory_descriptor_type, wdf.wdf_memory_descriptor_type, wdfmemory/WDF_MEMORY_DESCRIPTOR_TYPE, wdfmemory/WdfMemoryDescriptorTypeBuffer, wdfmemory/WdfMemoryDescriptorTypeHandle, wdfmemory/WdfMemoryDescriptorTypeInvalid, wdfmemory/WdfMemoryDescriptorTypeMdl
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
f1_keywords:
 - _WDF_MEMORY_DESCRIPTOR_TYPE
 - wdfmemory/_WDF_MEMORY_DESCRIPTOR_TYPE
 - WDF_MEMORY_DESCRIPTOR_TYPE
 - wdfmemory/WDF_MEMORY_DESCRIPTOR_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfmemory.h
api_name:
 - WDF_MEMORY_DESCRIPTOR_TYPE
---

# _WDF_MEMORY_DESCRIPTOR_TYPE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_MEMORY_DESCRIPTOR_TYPE</b> enumeration identifies the types of memory descriptions that a <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure can specify.

## -enum-fields

### -field WdfMemoryDescriptorTypeInvalid

Reserved for internal use only.

### -field WdfMemoryDescriptorTypeBuffer

The <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure contains a buffer description.

### -field WdfMemoryDescriptorTypeMdl

The <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure contains a memory descriptor list (MDL).

### -field WdfMemoryDescriptorTypeHandle

The <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure contains a handle to a memory object.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a>