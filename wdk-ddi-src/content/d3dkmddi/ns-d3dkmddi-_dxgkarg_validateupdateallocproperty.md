---
UID: NS:d3dkmddi._DXGKARG_VALIDATEUPDATEALLOCPROPERTY
title: DXGKARG_VALIDATEUPDATEALLOCPROPERTY (d3dkmddi.h)
description: Learn more about the DXGARG_VALIDATEUPDATEALLOCPROPERTY structure.
ms.date: 06/09/2023
keywords: ["DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure"]
ms.keywords: DXGKARG_VALIDATEUPDATEALLOCPROPERTY, DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure [Display Devices], _DXGKARG_VALIDATEUPDATEALLOCPROPERTY, d3dkmddi/DXGKARG_VALIDATEUPDATEALLOCPROPERTY, display.dxgkarg_validateupdateallocproperty
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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

The flags that will be used to update the allocation.

### -field SetAccessedPhysically

A UINT value that specifies whether the allocation is accessed by its physical address.

Setting this member is equivalent to setting the first bit of the 32-bit **PropertyMaskValue** member (0x00000001).

### -field SetSupportedSegmentSet

A UINT value that specifies whether the supported segment is set to a new value.

Setting this member is equivalent to setting the second bit of the 32-bit **PropertyMaskValue** member (0x00000010).

### -field SetPreferredSegment

A UINT value that specifies whether the preferred segment is set to a new value.

Setting this member is equivalent to setting the third bit of the 32-bit **PropertyMaskValue** member (0x00000100).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFFE) of the 32-bit **PropertyMaskValue** member to zeros.

### -field PropertyMaskValue

A member in the union that is contained in D3DDDI_UPDATEALLOCPROPERTY that can hold one 32-bit value that identifies how to update an allocation.
