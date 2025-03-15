---
UID: NS:d3dkmddi._DXGKARG_VALIDATEUPDATEALLOCPROPERTY
title: DXGKARG_VALIDATEUPDATEALLOCPROPERTY (d3dkmddi.h)
description: Learn more about the DXGARG_VALIDATEUPDATEALLOCPROPERTY structure.
ms.date: 12/17/2024
keywords: ["DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure"]
ms.keywords: DXGKARG_VALIDATEUPDATEALLOCPROPERTY, DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure [Display Devices], _DXGKARG_VALIDATEUPDATEALLOCPROPERTY, d3dkmddi/DXGKARG_VALIDATEUPDATEALLOCPROPERTY, display.dxgkarg_validateupdateallocproperty
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607 (WDDM 2.1)
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
tech.root: display
req.typenames: DXGKARG_VALIDATEUPDATEALLOCPROPERTY
f1_keywords:
 - _DXGKARG_VALIDATEUPDATEALLOCPROPERTY
 - d3dkmddi/_DXGKARG_VALIDATEUPDATEALLOCPROPERTY
 - DXGKARG_VALIDATEUPDATEALLOCPROPERTY
 - d3dkmddi/DXGKARG_VALIDATEUPDATEALLOCPROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_VALIDATEUPDATEALLOCPROPERTY
 - DXGKARG_VALIDATEUPDATEALLOCPROPERTY
---

# DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure

## -description

The **DXGKARG_VALIDATEUPDATEALLOCPROPERTY** structure holds the information needed to validate the parameters to update the properties of an allocation.

## -struct-fields

### -field hAllocation [in]

A handle to the allocation that will be updated.

### -field SupportedSegmentSet [in]

An index for the new supported segment set. If the current supported segment set is the same, then this will be ignored.

### -field PreferredSegment [in]

An index for the new preferred segment set. If the current preferred segment set is the same, then this will be ignored.

### -field Flags [in]

A [**D3DDDI_UPDATEALLOCPROPERTY_FLAGS**](../d3dukmdt/ns-d3dukmdt-d3dddi_updateallocproperty_flags.md) structure with flags that specify how to update the allocation's properties.

### -field SetAccessedPhysically

A UINT value that specifies whether the allocation is accessed by its physical address.

### -field SetSupportedSegmentSet

A UINT value that specifies whether the supported segment is set to a new value.

### -field SetPreferredSegment

A UINT value that specifies whether the preferred segment is set to a new value.

### -field Reserved

This member is reserved and should be set to zero.

### -field PropertyMaskValue

An alternative way to access the property mask values.

## -see-also

[**DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY**](nc-d3dkmddi-dxgkddi_validateupdateallocationproperty.md)
