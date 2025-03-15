---
UID: NC:d3dkmddi.DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
title: DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA (d3dkmddi.h)
description: Learn more about the DxgkDdiGetStandardAllocationDriverData function.
ms.date: 11/08/2024
keywords: ["DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
 - d3dkmddi/DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA
---

# DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA callback function

## -description

The **DxgkDdiGetStandardAllocationDriverData** function returns a description of a standard allocation type.

## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The kernel-mode display driver (KMD) previously provided this handle to *Dxgkrnl* in its [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pGetStandardAllocationDriverData [in/out]

A pointer to a[**DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA**](ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md) structure that describes a standard allocation.

## -returns

**DxgkDdiGetStandardAllocationDriverData** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS   | **DxgkDdiGetStandardAllocationDriverData** successfully returned a description of the standard allocation type.|
| STATUS_NO_MEMORY | **DxgkDdiGetStandardAllocationDriverData** couldn't allocate memory that was required for it to complete.|

## -remarks

*Standard allocation types* are allocations that must be created in kernel mode without communication from the user-mode display driver.

*Dxgkrnl* calls the kernel mode driver's (KMD's) **DxgkDdiGetStandardAllocationDriverData** function to generate a description of the standard allocation type that the **pGetStandardAllocationDriverData** parameter specifies. KMD returns the description of the allocation type in the **pAllocationPrivateDriverData** and **pResourcePrivateDriverData** members of the [**DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA**](ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md) structure that the **pGetStandardAllocationDriverData** parameter points to. *Dxgkrnl* subsequently passes the description to the [**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md) function to actually create the allocation.

Beginning with Windows 7, if KMD processes a call to the **DxgkDdiGetStandardAllocationDriverData** function to create allocations for GDI hardware acceleration, the driver should set the pitch of the allocation for CPU visible allocations, **pGetStandardAllocationDriverData->****pCreateGdiSurfaceData****->****Pitch**.

**DxgkDdiGetStandardAllocationDriverData** should be made pageable.

## -see-also

[**DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA**](ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)
