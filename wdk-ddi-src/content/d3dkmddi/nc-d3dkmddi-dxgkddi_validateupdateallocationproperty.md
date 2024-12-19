---
UID: NC:d3dkmddi.DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY
tech.root: display
title: DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY
ms.date: 12/17/2024
targetos: Windows
description: Learn more about the DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL or less
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1607 (WDDM 2.1)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY
f1_keywords:
 - DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY
 - d3dkmddi/DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY
---

## -description

The **DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY** function validates the update of an allocation property.

## -parameters

### -param hAdapter

[in] Handle to the display adapter that is associated with the allocation.

### -param pValidateUpdateAllocProperty

[in] A pointer to a [**DXGKARG_VALIDATEUPDATEALLOCATIONPROPERTY**](ns-d3dkmddi-_dxgkarg_validateupdateallocproperty.md) structure that describes the allocation property to be validated for update.

## -returns

**DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY** returns STATUS_SUCCESS if the allocation property can be updated; otherwise, it returns an appropriate error code.

## -see-also

[**DXGKARG_VALIDATEUPDATEALLOCATIONPROPERTY**](ns-d3dkmddi-_dxgkarg_validateupdateallocproperty.md)
