---
UID: NC:d3dumddi.PFND3DDDI_DEALLOCATECB
title: PFND3DDDI_DEALLOCATECB (d3dumddi.h)
description: The pfnDeallocateCb callback function releases allocations or a kernel-mode resource object if the resource object was created.
old-location: display\pfndeallocatecb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DEALLOCATECB callback function"]
ms.keywords: D3Druntime_Functions_0162df86-f479-45d9-887b-75f05de150f9.xml, PFND3DDDI_DEALLOCATECB, PFND3DDDI_DEALLOCATECB callback, d3dumddi/pfnDeallocateCb, display.pfndeallocatecb, pfnDeallocateCb, pfnDeallocateCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_DEALLOCATECB
 - d3dumddi/PFND3DDDI_DEALLOCATECB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnDeallocateCb
product:
 - Windows
---

# PFND3DDDI_DEALLOCATECB callback function


## -description

The <b>pfnDeallocateCb</b> callback function releases allocations or a kernel-mode resource object if the resource object was created.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_deallocate">D3DDDICB_DEALLOCATE</a> structure that describes the resource to release.

## -returns

<b>pfnDeallocateCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The memory was successfully released.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|


This function might also return other HRESULT values.

## -remarks

The user-mode display driver can release allocations in the following ways: 

<ul>
<li>
Individually, by setting the <b>hResource</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_deallocate">D3DDDICB_DEALLOCATE</a> structure that is pointed to by <i>pData </i>to <b>NULL</b> and populating the array in the <b>HandleList</b> member of D3DDDICB_DEALLOCATE with handles of the allocations to release 

</li>
<li>
In a group, by setting <b>hResource</b> to a resource handle whose allocations are to be released. If <b>hResource</b> is non-<b>NULL</b>, the <b>HandleList</b> and <b>NumAllocations</b> members of D3DDDICB_DEALLOCATE are ignored. 

</li>
</ul>
Note that if the user-mode display driver sets <b>hResource</b> to <b>NULL</b> and populates all array elements in <b>HandleList</b> to release all allocations, the driver must subsequently call the <b>pfnDeallocateCb</b> function again to only release the resource by setting <b>hResource</b> to the handle to the resource.

Note that the <b>pfnDeallocateCb</b> function is distinct from the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyresource">DestroyResource</a> or <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a> function. However, the user-mode display driver typically calls <b>pfnDeallocateCb</b> in response to a call to its <i>DestroyResource</i> or <b>DestroyResource(D3D10)</b> function. 

<b>Direct3D Version 9 Note:  </b>For more information about creating and destroying resources, see <a href="/windows-hardware/drivers/display/handling-resource-creation-and-destruction">Handling Resource Creation and Destruction</a>.

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnDeallocateCb</b>, see <a href="/windows-hardware/drivers/display/changes-from-direct3d-10">Changes from Direct3D 10</a>.

The following code example shows how to release a resource.

```
    D3DDDICB_DEALLOCATE deAllocCB;
    HRESULT             hr;
    D3DKMT_HANDLE       hKMAllocHandle;

    memset(&deAllocCB, 0, sizeof(deAllocCB));

    deAllocCB.hResource = m_hCurResRuntime;

    hr = m_d3dCallbacks.pfnDeallocateCb(m_hD3D, &deAllocCB);
    if ((m_hCurResRuntime) && (SUCCEEDED(hr))) {
        m_bCurResFreed = TRUE;
    }
```

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_deallocate">D3DDDICB_DEALLOCATE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroyresource">DestroyResource</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a>
