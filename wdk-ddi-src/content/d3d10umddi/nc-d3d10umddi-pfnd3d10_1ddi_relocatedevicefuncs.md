---
UID: NC:d3d10umddi.PFND3D10_1DDI_RELOCATEDEVICEFUNCS
title: PFND3D10_1DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The RelocateDeviceFuncs(D3D10_1) function notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d10_1_.htm
old-project: display
ms.assetid: 0141badb-0d2d-433f-950f-bf169087c574
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10_1DDI_RELOCATEDEVICEFUNCS, RelocateDeviceFuncs_D3D10_1, RelocateDeviceFuncs_D3D10_1 callback function [Display Devices], UserModeDisplayDriverDx10_Functions_5798bcfe-7d15-407d-b7c2-cfe907e94991.xml, d3d10umddi/RelocateDeviceFuncs_D3D10_1, display.relocatedevicefuncs_d3d10_1_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RelocateDeviceFuncs(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	RelocateDeviceFuncs_D3D10_1
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10_1DDI_RELOCATEDEVICEFUNCS callback


## -description


The <i>RelocateDeviceFuncs(D3D10_1)</i> function notifies the user-mode display driver about the new location of the driver function table. 


## -prototype


````
PFND3D10_1DDI_RELOCATEDEVICEFUNCS RelocateDeviceFuncs_D3D10_1;

VOID APIENTRY RelocateDeviceFuncs_D3D10_1(
  _In_ D3D10DDI_HDEVICE              hDevice,
  _In_ struct D3D10_1DDI_DEVICEFUNCS *pDeviceFunctions
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pDeviceFunctions [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. 




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D10_1)</i> function to replace function pointers in the driver function table. 




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>



 

 


