---
UID: NC:d3dumddi.PFND3DDDI_QUERYRESIDENCYCB
title: PFND3DDDI_QUERYRESIDENCYCB
author: windows-driver-content
description: The pfnQueryResidencyCb function queries the residency status of a resource or list of allocations.
old-location: display\pfnqueryresidencycb.htm
old-project: display
ms.assetid: 707ba050-e70c-49f8-aac0-0bcc8fe9bf8b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnQueryResidencyCb
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_QUERYRESIDENCYCB callback



## -description
The <b>pfnQueryResidencyCb</b> function queries the residency status of a resource or list of allocations.



## -prototype

````
PFND3DDDI_QUERYRESIDENCYCB pfnQueryResidencyCb;

__checkReturn HRESULT APIENTRY pfnQueryResidencyCb(
  _In_          HANDLE                  hDevice,
  _Inout_ const D3DDDICB_QUERYRESIDENCY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_queryresidency.md">D3DDDICB_QUERYRESIDENCY</a> structure that describes the residency status of a resource or list of allocations.


## -returns
<b>pfnQueryResidencyCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The residency status was successfully returned.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.


## -remarks
The user-mode display driver can call the <b>pfnQueryResidencyCb</b> function to query the residency status of allocations either through a resource or through a list of allocations. If the driver queries the residency status of allocations through a resource, all of the allocations that belong to the resource are queried. Typically, the user-mode display driver queries the residency of a resource or list of allocations after the Microsoft Direct3D runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresourceresidency.md">QueryResourceResidency</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a> function to determine the residency of a resource. However, the user-mode display driver can query the residency of a resource or list of allocations at any time. 

The following code example shows how to query for residency status.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_queryresidency.md">D3DDDICB_QUERYRESIDENCY</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresourceresidency.md">QueryResourceResidency</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_QUERYRESIDENCYCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

