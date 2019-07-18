---
UID: NS:d3d10umddi.D3D10DDIARG_OPENRESOURCE
title: D3D10DDIARG_OPENRESOURCE (d3d10umddi.h)
description: The D3D10DDIARG_OPENRESOURCE structure contains information for opening a shared resource.
old-location: display\d3d10ddiarg_openresource.htm
ms.assetid: acd1a957-9a1f-48a5-849b-e0cb9f8e05b6
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_OPENRESOURCE, D3D10DDIARG_OPENRESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_bb0f1769-190c-4500-8efa-9ed3eab771f7.xml, d3d10umddi/D3D10DDIARG_OPENRESOURCE, display.d3d10ddiarg_openresource
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_OPENRESOURCE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_OPENRESOURCE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_OPENRESOURCE
---

# D3D10DDIARG_OPENRESOURCE structure


## -description


The D3D10DDIARG_OPENRESOURCE structure contains information for opening a shared resource.


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that the <b>pOpenAllocationInfo</b> member specifies. <b>NumAllocations</b> represents the number of allocations to open.


### -field pOpenAllocationInfo2

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field pOpenAllocationInfo

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structures that describe the allocations in the resource to open.


### -field hKMResource

[in] A D3D10DDI_HKMRESOURCE data type that represents a kernel-mode handle to the resource that is associated with the allocations. 

This kernel-mode handle represents an existing shared resource that was previously created through a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function. 

The user-mode display driver can insert the kernel-mode resource handle in the command stream for subsequent use by the display miniport driver.


### -field pPrivateDriverData

[in] A pointer to private data that was passed to the display miniport driver when the resource was created. This data is per resource and not per allocation like the private data in each allocation's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a> structure. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_openallocationinfo">D3DDDI_OPENALLOCATIONINFO</a>
 

 

