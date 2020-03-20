---
UID: NS:d3dkmddi._DXGKARG_VALIDATEUPDATEALLOCPROPERTY
title: _DXGKARG_VALIDATEUPDATEALLOCPROPERTY (d3dkmddi.h)
description: The DXGARG_VALIDATEUPDATEALLOCPROPERTY structure holds the information needed to validate the parameters to update the properties of an allocation.
old-location: display\dxgkarg_validateupdateallocproperty.htm
ms.assetid: EC9654B8-06AA-43C8-A159-F176BDE4E015
ms.date: 05/10/2018
keywords: ["_DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure"]
ms.keywords: DXGKARG_VALIDATEUPDATEALLOCPROPERTY, DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure [Display Devices], _DXGKARG_VALIDATEUPDATEALLOCPROPERTY, d3dkmddi/DXGKARG_VALIDATEUPDATEALLOCPROPERTY, display.dxgkarg_validateupdateallocproperty
f1_keywords:
 - "d3dkmddi/DXGKARG_VALIDATEUPDATEALLOCPROPERTY"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARG_VALIDATEUPDATEALLOCPROPERTY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_VALIDATEUPDATEALLOCPROPERTY
---

# _DXGKARG_VALIDATEUPDATEALLOCPROPERTY structure


## -description


The DXGARG_VALIDATEUPDATEALLOCPROPERTY structure holds the information needed to validate the parameters to update the properties of an allocation.


## -struct-fields




### -field hAllocation

[in] A Handle to the allocation that will be updated.


### -field SupportedSegmentSet

[in] An index for the new supported segment set. If the current supported segment set is the same, then this will be ignored.


### -field PreferredSegment

[in] An index for the new preferred segment set. If the current preferred segment set is the same, then this will be ignored.


### -field Flags

[in] The flags that will be used to update the allocation.


### -field SetAccessedPhysically

A UINT value that specifies whether the allocation is accessed by its physical address.

Setting this member is equivalent to setting the first bit of the 32-bit <b>PropertyMaskValue</b> member (0x00000001).


### -field SetSupportedSegmentSet

A UINT value that specifies whether the supported segment is set to a new value.

Setting this member is equivalent to setting the second bit of the 32-bit <b>PropertyMaskValue</b> member (0x00000010).


### -field SetPreferredSegment

A UINT value that specifies whether the preferred segment is set to a new value.

Setting this member is equivalent to setting the third bit of the 32-bit <b>PropertyMaskValue</b> member (0x00000100).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFFE) of the 32-bit <b>PropertyMaskValue</b> member to zeros.


### -field PropertyMaskValue

A member in the union that is contained in D3DDDI_UPDATEALLOCPROPERTY that can hold one 32-bit value that identifies how to update an allocation.

