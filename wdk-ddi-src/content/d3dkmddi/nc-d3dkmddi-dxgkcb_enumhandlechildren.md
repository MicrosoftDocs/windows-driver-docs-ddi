---
UID: NC:d3dkmddi.DXGKCB_ENUMHANDLECHILDREN
title: DXGKCB_ENUMHANDLECHILDREN (d3dkmddi.h)
description: The DxgkCbEnumHandleChildren function enumerates all of the allocations that are associated with a given resource, one allocation at a time.
old-location: display\dxgkcbenumhandlechildren.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_ENUMHANDLECHILDREN callback function"]
ms.keywords: DXGKCB_ENUMHANDLECHILDREN, DXGKCB_ENUMHANDLECHILDREN callback, DpFunctions_9690e256-00e7-4c6e-88cc-d2e1c32580a2.xml, DxgkCbEnumHandleChildren, DxgkCbEnumHandleChildren callback function [Display Devices], d3dkmddi/DxgkCbEnumHandleChildren, display.dxgkcbenumhandlechildren
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_ENUMHANDLECHILDREN
 - d3dkmddi/DXGKCB_ENUMHANDLECHILDREN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ENUMHANDLECHILDREN
---

# DXGKCB_ENUMHANDLECHILDREN callback function

## -description

**DXGKCB_ENUMHANDLECHILDREN** enumerates the allocations associated with a given resource, one allocation at a time.

## -parameters

### -param pData [in]

Pointer to a [**DXGKARGCB_ENUMHANDLECHILDREN**](ns-d3dkmddi-_dxgkargcb_enumhandlechildren.md) structure that describes the parent resource and the index of the child allocation to retrieve.

## -returns

**DXGKCB_ENUMHANDLECHILDREN** returns the *Dxgkrnl*-specific handle to the child allocation that **pData** describes. To retrieve the device-specific *data* for the handle, the display miniport driver must call the [**DXGKCB_GETHANDLEDATA**](nc-d3dkmddi-dxgkcb_gethandledata.md) function.

**DXGKCB_ENUMHANDLECHILDREN** returns a NULL handle if the child-allocation index value supplied in the **Index** member of the [**DXGKARGCB_ENUMHANDLECHILDREN**](ns-d3dkmddi-_dxgkargcb_enumhandlechildren.md) structure exceeds the number of allocations that are associated with the parent resource. If **DXGKCB_ENUMHANDLECHILDREN** unexpectedly returns a NULL handle, the DirectX graphics kernel subsystem was unable to resolve the handle to the parent resource, for a reason such as the following possibilities:

* An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug.
* Allocations had lifetime issues.

If a **NULL** handle is returned unexpectedly, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.

## -remarks

A display miniport driver can call **DXGKCB_ENUMHANDLECHILDREN** in a loop to enumerate all of the allocations that are associated with a resource.

The allocation handle indices are zero-based. If the display miniport driver sets [**pData->Index**](ns-d3dkmddi-_dxgkargcb_enumhandlechildren.md) to 0, **DXGKCB_ENUMHANDLECHILDREN** returns the first allocation handle; if **Index** is set to 1, **DXGKCB_ENUMHANDLECHILDREN** returns the second allocation handle; and so on. If **Index** is greater than the number of allocations that are associated with the resource, **DXGKCB_ENUMHANDLECHILDREN** returns **NULL**.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_ENUMHANDLECHILDREN**](ns-d3dkmddi-_dxgkargcb_enumhandlechildren.md) and then call **DxgkCbEnumHandleChildren** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_ENUMHANDLECHILDREN**](ns-d3dkmddi-_dxgkargcb_enumhandlechildren.md)

[**DXGKCB_GETHANDLEDATA**](nc-d3dkmddi-dxgkcb_gethandledata.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
