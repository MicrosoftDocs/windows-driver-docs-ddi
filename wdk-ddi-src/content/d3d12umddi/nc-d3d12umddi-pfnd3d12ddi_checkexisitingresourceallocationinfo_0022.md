---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
title: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
author: windows-driver-content
description: The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information.
old-location: display\pfnd3d12ddi_checkexisitingresourceallocationinfo_0022.htm
old-project: display
ms.assetid: 428F23B4-3032-4BD9-A1C1-104BB2648F89
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnCheckExistingResourceAllocationInfo
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback



## -description
The <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt799844">pfnCheckExistingResourceAllocationInfo</a> callback function supports checking existing resource allocation information.



## -prototype

````
PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 pfnCheckExistingResourceAllocationInfo;

VOID APIENTRY* pfnCheckExistingResourceAllocationInfo(
        D3D10DDI_HDEVICE                       hDevice,
        D3D10DDI_HRESOURCE                     hResource,
  _Out_ D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 *pInfo
)
{ ... }
````


## -parameters

### -param hDevice 

A device handle.


### -param hResource 

A resource handle.


### -param pInfo [out]

Information for resource allocation. 


## -returns
This callback function does not return a value.


## -remarks
This callback function is part of a two step process of resource creation. After the <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022.md">pfnCheckResourceAllocationInfo</a> callback function, the resource is created. During resource creation, the layout is never _UNDEFINED, since the driver will have returned a resolved texture layout. 


## -see-also
<dl>
<dt>
<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0022.md">pfnCheckResourceAllocationInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

