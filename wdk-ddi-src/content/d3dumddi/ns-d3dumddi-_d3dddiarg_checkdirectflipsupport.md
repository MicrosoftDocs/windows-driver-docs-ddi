---
UID: NS:d3dumddi._D3DDDIARG_CHECKDIRECTFLIPSUPPORT
title: "_D3DDDIARG_CHECKDIRECTFLIPSUPPORT"
author: windows-driver-content
description: Specifies resources used for Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager's (DWM) managed primary allocations.
old-location: display\d3dddiarg_checkdirectflipsupport.htm
old-project: display
ms.assetid: 70df85b6-286a-45a2-813d-adb54daee122
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_CHECKDIRECTFLIPSUPPORT, D3DDDIARG_CHECKDIRECTFLIPSUPPORT structure [Display Devices], _D3DDDIARG_CHECKDIRECTFLIPSUPPORT, d3dumddi/D3DDDIARG_CHECKDIRECTFLIPSUPPORT, display.d3dddiarg_checkdirectflipsupport
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CHECKDIRECTFLIPSUPPORT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

