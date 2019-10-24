---
UID: NS:d3dumddi._D3DDDICB_GETMULTISAMPLEMETHODLIST
title: _D3DDDICB_GETMULTISAMPLEMETHODLIST (d3dumddi.h)
description: The D3DDDICB_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation.
old-location: display\d3dddicb_getmultisamplemethodlist.htm
tech.root: display
ms.assetid: 07cabd0e-5b5c-42ff-9b2a-57bec527d690
ms.date: 05/10/2018
ms.keywords: D3DDDICB_GETMULTISAMPLEMETHODLIST, D3DDDICB_GETMULTISAMPLEMETHODLIST structure [Display Devices], D3D_param_Structs_11da91d5-a4e6-4d24-b2b1-3645003ff25e.xml, _D3DDDICB_GETMULTISAMPLEMETHODLIST, d3dumddi/D3DDDICB_GETMULTISAMPLEMETHODLIST, display.d3dddicb_getmultisamplemethodlist
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDICB_GETMULTISAMPLEMETHODLIST"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDICB_GETMULTISAMPLEMETHODLIST
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_GETMULTISAMPLEMETHODLIST
---

# _D3DDDICB_GETMULTISAMPLEMETHODLIST structure


## -description


The D3DDDICB_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the allocation is on. 


### -field Width

[in] The width of the allocation, in pixels.


### -field Height

[in] The height of the allocation, in pixels.


### -field Format

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the allocation.


### -field pMethodList

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_multisamplingmethod">D3DDDI_MULTISAMPLINGMETHOD</a> structures that describe the list of multiple-sampling methods that are used for the allocation or <b>NULL</b>.


### -field MethodCount

[in/out] On input, the number of elements that the buffer at <b>pMethodList</b> can hold. On output, this member specifies the required number of elements that the buffer at <b>pMethodList</b> should hold. 


## -remarks



If the runtime returns a non-<b>NULL</b> value in the <b>pMethodList</b> member, the runtime returns a value in the <b>MethodCount</b> member that represents the number of elements that the array can hold. If the runtime returns <b>NULL</b> at <b>pMethodList</b>, the runtime returns a value in <b>MethodCount</b> that represents the size of the array buffer that is required, in number of elements. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_multisamplingmethod">D3DDDI_MULTISAMPLINGMETHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb">pfnGetMultisampleMethodListCb</a>
 

 

