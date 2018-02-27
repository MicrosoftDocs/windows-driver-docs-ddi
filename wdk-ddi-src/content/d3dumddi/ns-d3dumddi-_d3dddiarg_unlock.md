---
UID: NS:d3dumddi._D3DDDIARG_UNLOCK
title: "_D3DDDIARG_UNLOCK"
author: windows-driver-content
description: The D3DDDIARG_UNLOCK structure describes a resource or a surface within the resource to unlock.
old-location: display\d3dddiarg_unlock.htm
old-project: display
ms.assetid: e6e0b0fd-be80-4c44-9d7d-1b9476b44b65
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_UNLOCK
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_UNLOCK
---

# _D3DDDIARG_UNLOCK structure


## -description


The D3DDDIARG_UNLOCK structure describes a resource or a surface within the resource to unlock. 


## -syntax


````
typedef struct _D3DDDIARG_UNLOCK {
  HANDLE             hResource;
  UINT               SubResourceIndex;
  D3DDDI_UNLOCKFLAGS Flags;
} D3DDDIARG_UNLOCK;
````


## -struct-fields




### -field hResource

[in] A handle to the resource to be unlocked. 


### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource or surface to be unlocked.


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_unlockflags.md">D3DDDI_UNLOCKFLAGS</a> structure that indicates, in bit-field flags, how to unlock the resource.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock.md">Unlock</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_unlockflags.md">D3DDDI_UNLOCKFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_UNLOCK structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

