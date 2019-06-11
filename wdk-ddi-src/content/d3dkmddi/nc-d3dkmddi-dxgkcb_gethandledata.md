---
UID: NC:d3dkmddi.DXGKCB_GETHANDLEDATA
title: DXGKCB_GETHANDLEDATA (d3dkmddi.h)
description: The DxgkCbGetHandleData function retrieves the private data that is associated with an allocation.
old-location: display\dxgkcbgethandledata.htm
ms.assetid: 144429e5-34e6-4416-980e-2838e8f9e415
ms.date: 05/10/2018
ms.keywords: DXGKCB_GETHANDLEDATA, DXGKCB_GETHANDLEDATA callback, DpFunctions_74327569-9de1-4396-928b-0350e622740f.xml, DxgkCbGetHandleData, DxgkCbGetHandleData callback function [Display Devices], d3dkmddi/DxgkCbGetHandleData, display.dxgkcbgethandledata
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkCbGetHandleData
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_GETHANDLEDATA callback function


## -description


The <i>DxgkCbGetHandleData</i> function retrieves the private data that is associated with an allocation.


## -parameters










#### -param

*pData*

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure that describes the allocation data to retrieve.


## -returns



<i>DxgkCbGetHandleData</i> returns a buffer that contains the private data for the allocation.

If <i>DxgkCbGetHandleData</i> returns a <b>NULL</b> pointer, the Microsoft DirectX graphics kernel subsystem was unable to resolve the handle that is supplied in the <b>hObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure to private data because, for example, of the following possible reasons: 

<ul>
<li>An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug. </li>
<li>Allocations had lifetime issues. </li>
</ul>
If a <b>NULL</b> pointer is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.




## -remarks



When the DirectX graphics kernel subsystem calls the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function to create handles to allocations, the display miniport driver can create private data for each allocation handle. The display miniport driver can subsequently call the <b>DxgkCbGetHandleData</b> function to retrieve private data for each graphics subsystem-specific handle. Therefore, the display miniport driver is not required to maintain a private allocation handle table. 

If the <b>DeviceSpecific</b> bit-field flag is set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a> structure that <i>pData</i> points to, <b>DxgkCbGetHandleData</b> returns the device-specific data that is associated with the device-specific handle that the driver returned from the call to its <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function. Note that the <b>DeviceSpecific</b> bit-field flag is valid only if the display miniport driver also sets the <b>Type</b> member of DXGKARGCB_GETHANDLEDATA to the DXGK_HANDLE_ALLOCATION enumeration value for the handle in the <b>hObject</b> member of DXGKARGCB_GETHANDLEDATA.


#### Examples

The following code example shows an implementation of <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> in which <b>DxgkCbGetHandleData</b> is called.

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

    for (dwIdx=0; dwIdx &lt; pDDIDAData->NumAllocations; dwIdx++) {
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557534">DXGKARGCB_GETHANDLEDATA</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>
 

 

