---
UID: NS:d3dumddi._D3DDDIARG_UNLOCKASYNC
title: "_D3DDDIARG_UNLOCKASYNC"
author: windows-driver-content
description: The D3DDDIARG_UNLOCKASYNC structure describes a resource or a surface within the resource to unlock.
old-location: display\d3dddiarg_unlockasync.htm
old-project: display
ms.assetid: 27d4a7fa-ac2a-4049-8c9f-5ac9338c70b3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DDDIARG_UNLOCKASYNC, D3DDDIARG_UNLOCKASYNC structure [Display Devices], display.d3dddiarg_unlockasync, D3DDDIARG_UNLOCKASYNC, d3dumddi/D3DDDIARG_UNLOCKASYNC, UMDisplayDriver_param_Structs_1b08f2e6-73cd-4390-a9a2-54e604ca5012.xml"
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
-	D3DDDIARG_UNLOCKASYNC
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_UNLOCKASYNC
---

# _D3DDDIARG_UNLOCKASYNC structure


## -description


The D3DDDIARG_UNLOCKASYNC structure describes a resource or a surface within the resource to unlock. 


## -syntax


````
typedef struct _D3DDDIARG_UNLOCKASYNC {
  HANDLE                  hResource;
  UINT                    SubResourceIndex;
  D3DDDI_UNLOCKASYNCFLAGS Flags;
} D3DDDIARG_UNLOCKASYNC;
````


## -struct-fields




### -field hResource

[in] A handle to the resource to be unlocked. 


### -field SubResourceIndex

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be unlocked.


### -field Flags

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_unlockasyncflags.md">D3DDDI_UNLOCKASYNCFLAGS</a> structure that indicates, in bit-field flags, how to unlock the resource.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockasync.md">UnlockAsync</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_UNLOCKASYNC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

