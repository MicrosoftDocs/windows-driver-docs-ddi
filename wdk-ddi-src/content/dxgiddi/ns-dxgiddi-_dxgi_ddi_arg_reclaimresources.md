---
UID: NS:dxgiddi._DXGI_DDI_ARG_RECLAIMRESOURCES
title: _DXGI_DDI_ARG_RECLAIMRESOURCES (dxgiddi.h)
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the pfnReclaimResources function by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\dxgi_ddi_arg_reclaimresources.htm
tech.root: display
ms.assetid: 43e34157-2cf1-4e2c-bcd8-c4425e89fb0f
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_ARG_RECLAIMRESOURCES, DXGI_DDI_ARG_RECLAIMRESOURCES structure [Display Devices], _DXGI_DDI_ARG_RECLAIMRESOURCES, display.dxgi_ddi_arg_reclaimresources, dxgiddi/DXGI_DDI_ARG_RECLAIMRESOURCES
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,WDDM 1.2 and later
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
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI_DDI_ARG_RECLAIMRESOURCES
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_RECLAIMRESOURCES
---

# _DXGI_DDI_ARG_RECLAIMRESOURCES structure


## -description


Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> function by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver offers resources for reuse.

The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> routine.


### -field pResources

[in] A pointer to an array of handles to the resources that are to be reclaimed.


### -field pDiscarded

[out] An optional array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the structure pointed to by <b>pResources</b>.

The driver sets each Boolean value to <b>TRUE</b> if the correponding resource was discarded, or to <b>FALSE</b> if not.

If <b>pDiscarded</b> is <b>NULL</b>, the driver can ignore it.


### -field Resources

[in] The number of elements in the arrays pointed to by <b>pResources</b> and <b>pDiscarded</b>.


## -see-also




<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>
 

 

