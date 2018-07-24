---
UID: NS:d3dumddi._D3DDDIARG_UNLOCK
title: "_D3DDDIARG_UNLOCK"
author: windows-driver-content
description: The D3DDDIARG_UNLOCK structure describes a resource or a surface within the resource to unlock.
old-location: display\d3dddiarg_unlock.htm
tech.root: display
ms.assetid: e6e0b0fd-be80-4c44-9d7d-1b9476b44b65
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_UNLOCK, D3DDDIARG_UNLOCK structure [Display Devices], UMDisplayDriver_param_Structs_ae4773cf-d43a-4468-8d6b-a4c4fa9b55fa.xml, _D3DDDIARG_UNLOCK, d3dumddi/D3DDDIARG_UNLOCK, display.d3dddiarg_unlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_UNLOCK
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_UNLOCK
---

# _D3DDDIARG_UNLOCK structure


## -description


The D3DDDIARG_UNLOCK structure describes a resource or a surface within the resource to unlock. 


## -struct-fields




### -field hResource

[in] A handle to the resource to be unlocked. 


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource or surface to be unlocked.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544680">D3DDDI_UNLOCKFLAGS</a> structure that indicates, in bit-field flags, how to unlock the resource.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544680">D3DDDI_UNLOCKFLAGS</a>



<a href="https://msdn.microsoft.com/23cc9c64-99d4-4602-a1b0-234fe7fcc3da">Unlock</a>
 

 

