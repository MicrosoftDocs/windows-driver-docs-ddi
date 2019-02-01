---
UID: NS:d3dumddi._D3DDDIARG_CHECKDIRECTFLIPSUPPORT
title: _D3DDDIARG_CHECKDIRECTFLIPSUPPORT (d3dumddi.h)
description: Specifies resources used for Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager's (DWM) managed primary allocations.
old-location: display\d3dddiarg_checkdirectflipsupport.htm
tech.root: display
ms.assetid: 70df85b6-286a-45a2-813d-adb54daee122
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CHECKDIRECTFLIPSUPPORT, D3DDDIARG_CHECKDIRECTFLIPSUPPORT structure [Display Devices], _D3DDDIARG_CHECKDIRECTFLIPSUPPORT, d3dumddi/D3DDDIARG_CHECKDIRECTFLIPSUPPORT, display.d3dddiarg_checkdirectflipsupport
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDIARG_CHECKDIRECTFLIPSUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CHECKDIRECTFLIPSUPPORT
---

# _D3DDDIARG_CHECKDIRECTFLIPSUPPORT structure


## -description


Specifies resources used for Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager's (DWM) managed primary allocations. This structure is pointed to by the <i>pData</i> parameter of the <a href="https://msdn.microsoft.com/BB909041-0194-4828-ACA2-E3F6B1974DBB">CheckDirectFlipSupport</a> function.


## -struct-fields




### -field hAppSwapchainResource

[in] A resource in the application's swapchain.


### -field hDWMSwapchainResource

[in] A resource in the DWM's swapchain.


### -field CheckDirectFlipFlags

[in] If this member has a value of <b>D3DDDI_CHECKDIRECTFLIP_IMMEDIATE</b>, seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.


### -field Supported

[out] Set to <b>TRUE</b> if the driver can seamlessly flip video memory between  an application's managed primary allocations and the DWM's managed primary allocations. Otherwise, set to <b>FALSE</b>.


## -see-also




<a href="https://msdn.microsoft.com/BB909041-0194-4828-ACA2-E3F6B1974DBB">CheckDirectFlipSupport</a>
 

 

