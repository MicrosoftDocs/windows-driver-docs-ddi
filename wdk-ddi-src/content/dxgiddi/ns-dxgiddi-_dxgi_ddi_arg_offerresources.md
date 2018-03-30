---
UID: NS:dxgiddi._DXGI_DDI_ARG_OFFERRESOURCES
title: "_DXGI_DDI_ARG_OFFERRESOURCES"
author: windows-driver-content
description: Describes video memory resources that the user-mode display driver offers for reuse. Used with the pfnOfferResources function. Used with the pfnReclaimResources function by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\dxgi_ddi_arg_offerresources.htm
old-project: display
ms.assetid: 54d53a48-b2e2-43f6-9e6d-c35c732b07d9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_ARG_OFFERRESOURCES, DXGI_DDI_ARG_OFFERRESOURCES structure [Display Devices], _DXGI_DDI_ARG_OFFERRESOURCES, display.dxgi_ddi_arg_offerresources, dxgiddi/DXGI_DDI_ARG_OFFERRESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	DXGI_DDI_ARG_OFFERRESOURCES
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_OFFERRESOURCES
---

# _DXGI_DDI_ARG_OFFERRESOURCES structure


## -description


Describes video memory resources that the user-mode display driver offers for reuse. Used with the <a href="https://msdn.microsoft.com/2E85EFB6-6116-4FE7-97E0-547FFD61B511">pfnOfferResources</a> function. Used with the <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> function by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) on which the driver offers resources for reuse.

The Direct3D runtime passed this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when it created the device by calling the <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> routine.


### -field pResources

[in] A pointer to an array of handles to the video memory resources that the driver offers.


### -field Resources

[in] The number of elements in the array pointed to by <b>pResources</b>.


### -field Priority

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh439275">D3DDDI_OFFER_PRIORITY</a> that indicates the importance of the resources pointed to by <b>pResources</b>.


## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439275">D3DDDI_OFFER_PRIORITY</a>



<a href="https://msdn.microsoft.com/2E85EFB6-6116-4FE7-97E0-547FFD61B511">pfnOfferResources</a>
 

 

