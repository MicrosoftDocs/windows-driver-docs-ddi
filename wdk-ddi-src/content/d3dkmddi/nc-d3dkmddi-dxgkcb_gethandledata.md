---
UID: NC:d3dkmddi.DXGKCB_GETHANDLEDATA
title: DXGKCB_GETHANDLEDATA (d3dkmddi.h)
description: The DxgkCbGetHandleData function retrieves the private data that is associated with an allocation.
old-location: display\dxgkcbgethandledata.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_GETHANDLEDATA callback function"]
ms.keywords: DXGKCB_GETHANDLEDATA, DXGKCB_GETHANDLEDATA callback, DpFunctions_74327569-9de1-4396-928b-0350e622740f.xml, DxgkCbGetHandleData, DxgkCbGetHandleData callback function [Display Devices], d3dkmddi/DxgkCbGetHandleData, display.dxgkcbgethandledata
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_GETHANDLEDATA
 - d3dkmddi/DXGKCB_GETHANDLEDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_GETHANDLEDATA
---

# DXGKCB_GETHANDLEDATA callback function

## -description

**DXGKCB_GETHANDLEDATA** retrieves the private data associated with an allocation.

## -parameters

## -param pData

[in] A pointer to a [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) structure that describes the allocation data to retrieve.

## -returns

**DXGKCB_GETHANDLEDATA** returns a buffer that contains the private data for the allocation.

If **DXGKCB_GETHANDLEDATA** returns a NULL pointer, the DirectX graphics kernel subsystem was unable to resolve the handle that is supplied in the **hObject** member of the [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) structure to private data for a reason such as the following possibilities:

* An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug.
* Allocations had lifetime issues.

If a NULL pointer is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.

## -remarks

When the DirectX graphics kernel subsystem calls the display miniport driver's [**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md) function to create handles to allocations, the display miniport driver can create private data for each allocation handle. The display miniport driver can subsequently call the **DXGKCB_GETHANDLEDATA** function to retrieve private data for each graphics subsystem-specific handle. Therefore, the display miniport driver is not required to maintain a private allocation handle table.

If the **DeviceSpecific** bit-field flag is set in the **Flags** member of the [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) structure that **pData** points to, **DXGKCB_GETHANDLEDATA** returns the device-specific data that is associated with the device-specific handle that the driver returned from the call to its [**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md) function. Note that the **DeviceSpecific** bit-field flag is valid only if the display miniport driver also sets the **Type** member of **DXGKARGCB_GETHANDLEDATA** to the **DXGK_HANDLE_ALLOCATION** enumeration value for the handle in the **hObject** member of **DXGKARGCB_GETHANDLEDATA**.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md) and then call **DxgkCbGetHandleData** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

### Example

The following code example shows an implementation of [**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md) in which **DXGKCB_GETHANDLEDATA** is called.

```cpp
NTSTATUS
DxgkDdiOpenAllocation(
    VOID    *InterfaceContext,
    CONST DXGKARG_OPENALLOCATION    *pDDIDAData)
{
    DWORD dwIdx;
    DXGKRNL_INTERFACE              *pCallback;
    PR2D3DDevice                    pR2D3DDev;
    PHW_DEVICE_EXTENSION            pAdapter;

    pR2D3DDev = (PR2D3DDevice)InterfaceContext;
    pAdapter  = (PHW_DEVICE_EXTENSION)pR2D3DDev->pAdapter;
    pCallback = &(pAdapter->ddiCallback);

    for (dwIdx=0; dwIdx < pDDIDAData->NumAllocations; dwIdx++) {
        DXGKARGCB_GETHANDLEDATA  getHandleData = {0};
        R2AllocationInfo*  pAllocInfo;

        getHandleData.hObject = pDDIDAData->pOpenAllocation[dwIdx].hAllocation;
        getHandleData.Type    = DXGK_HANDLE_ALLOCATION;
        pAllocInfo = (PR2AllocationInfo)pCallback->DxgkCbGetHandleData(&getHandleData);
        pDDIDAData->pOpenAllocation[dwIdx].hDeviceSpecificAllocation = (HANDLE)pAllocInfo;
        pAllocInfo->vidMemData.hAllocation = pDDIDAData->pOpenAllocation[dwIdx].hAllocation;
    }
    return STATUS_SUCCESS;
}
```

## -see-also

[**DXGKARGCB_GETHANDLEDATA**](ns-d3dkmddi-_dxgkargcb_gethandledata.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)

[**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
