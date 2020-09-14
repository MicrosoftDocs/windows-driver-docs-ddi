---
UID: NC:d3dumddi.PFND3DDDI_QUERYRESIDENCYCB
title: PFND3DDDI_QUERYRESIDENCYCB (d3dumddi.h)
description: The pfnQueryResidencyCb function queries the residency status of a resource or list of allocations.
old-location: display\pfnqueryresidencycb.htm
tech.root: display
ms.assetid: 707ba050-e70c-49f8-aac0-0bcc8fe9bf8b
ms.date: 05/10/2018
keywords: ["PFND3DDDI_QUERYRESIDENCYCB callback function"]
ms.keywords: D3Druntime_Functions_9c92da7d-b114-4aab-adfe-13b5afebb4c8.xml, PFND3DDDI_QUERYRESIDENCYCB, PFND3DDDI_QUERYRESIDENCYCB callback, d3dumddi/pfnQueryResidencyCb, display.pfnqueryresidencycb, pfnQueryResidencyCb, pfnQueryResidencyCb callback function [Display Devices]
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
 - PFND3DDDI_QUERYRESIDENCYCB
 - d3dumddi/PFND3DDDI_QUERYRESIDENCYCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnQueryResidencyCb
product:
 - Windows
---

# PFND3DDDI_QUERYRESIDENCYCB callback function


## -description

The <b>pfnQueryResidencyCb</b> function queries the residency status of a resource or list of allocations.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryresidency">D3DDDICB_QUERYRESIDENCY</a> structure that describes the residency status of a resource or list of allocations.

## -returns

<b>pfnQueryResidencyCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The residency status was successfully returned.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|


This function might also return other HRESULT values.

## -remarks

The user-mode display driver can call the <b>pfnQueryResidencyCb</b> function to query the residency status of allocations either through a resource or through a list of allocations. If the driver queries the residency status of allocations through a resource, all of the allocations that belong to the resource are queried. Typically, the user-mode display driver queries the residency of a resource or list of allocations after the Microsoft Direct3D runtime calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresourceresidency">QueryResourceResidency</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">QueryResourceResidencyDXGI</a> function to determine the residency of a resource. However, the user-mode display driver can query the residency of a resource or list of allocations at any time. 


#### Examples

The following code example shows how to query for residency status.

```cpp
HRESULT
CD3DContext::QueryResourceResidency(CONST D3DDDIARG_QUERYRESOURCERESIDENCY* pQRR)
{
    D3DDDICB_QUERYRESIDENCY queryRes;
    D3DDDI_RESIDENCYSTATUS  resStatus = (D3DDDI_RESIDENCYSTATUS)0;
    HRESULT hr;
    BOOL    bPartInSharedMem = FALSE;

    for (UINT i = 0; i < pQRR->NumResources; i++) {
        memset(&queryRes, 0, sizeof(queryRes));
        queryRes.hResource = m_RTbl[(DWORD)(DWORD_PTR)pQRR->pHandleList[i]].m_hResRuntime;
        if (! queryRes.hResource) {
            return (DDERR_INVALIDPARAMS);
        }
        queryRes.pResidencyStatus = &resStatus;
        hr = m_d3dCallbacks.pfnQueryResidencyCb(m_hD3D, &queryRes);
        if (FAILED(hr)) {
            return (hr);
        }
        switch (resStatus) {
        case D3DDDI_RESIDENCYSTATUS_NOTRESIDENT:
            return S_NOT_RESIDENT;
        case D3DDDI_RESIDENCYSTATUS_RESIDENTINSHAREDMEMORY:
            bPartInSharedMem = TRUE;
            break;
        case D3DDDI_RESIDENCYSTATUS_RESIDENTINGPUMEMORY:
            break;
        default:
            return DDERR_GENERIC;
        }
    }
    if (bPartInSharedMem) {
        return S_RESIDENT_IN_SHARED_MEMORY;
    }
    else {
        return  S_OK;
    }
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryresidency">D3DDDICB_QUERYRESIDENCY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryresourceresidency">QueryResourceResidency</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">QueryResourceResidencyDXGI</a>

