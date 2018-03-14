---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATERASTERIZERSTATE
title: PFND3D11_1DDI_CREATERASTERIZERSTATE
author: windows-driver-content
description: Creates a rasterizer state.
old-location: display\createrasterizerstate_d3d11_1_.htm
old-project: display
ms.assetid: 5640e1c9-6a38-4eca-9048-0bc9ff66c43c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateRasterizerState(D3D11_1), CreateRasterizerState(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATERASTERIZERSTATE, d3d10umddi/CreateRasterizerState(D3D11_1), display.createrasterizerstate_d3d11_1_, display.pfncreaterasterizerstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CreateRasterizerState(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATERASTERIZERSTATE callback


## -description


Creates a rasterizer state.


## -prototype


````
PFND3D11_1DDI_CREATERASTERIZERSTATE CreateRasterizerState(D3D11_1);

VOID APIENTRY* CreateRasterizerState(D3D11_1)(
             D3D10DDI_HDEVICE            hDevice,
  _In_ const D3D11_1_DDI_RASTERIZER_DESC *pRasterizerDesc,
             D3D10DDI_HRASTERIZERSTATE   hRasterizerState,
             D3D10DDI_HRTRASTERIZERSTATE hRTRasterizerState
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D10DDI_HRASTERIZERSTATE


### -param D3D10DDI_HRTRASTERIZERSTATE








#### - hDevice

A handle to the display device (graphics context).


#### - hRTRasterizerState

A handle to the rasterizer state that the driver should use when it calls back into the Direct3D runtime.


#### - hRasterizerState

A handle to the driver's private data for the rasterizer state. The driver returns the size, in bytes, of the memory region that the Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize(D3D11_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its rasterizer state object.


#### - pRasterizerDesc [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc.md">D3D11_1_DDI_RASTERIZER_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a rasterizer state.


## -returns



The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a> function to destroy the handle that the <i>hRasterizerState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of rasterizer-state objects on a device at a time. 




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc.md">D3D11_1_DDI_RASTERIZER_DESC</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize(D3D11_1)</a>



 

 


