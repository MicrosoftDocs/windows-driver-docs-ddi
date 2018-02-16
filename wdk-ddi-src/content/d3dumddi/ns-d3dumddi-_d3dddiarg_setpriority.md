---
UID: NS:d3dumddi._D3DDDIARG_SETPRIORITY
title: "_D3DDDIARG_SETPRIORITY"
author: windows-driver-content
description: The D3DDDIARG_SETPRIORITY structure describes the priority level to set for a managed texture.
old-location: display\d3dddiarg_setpriority.htm
old-project: display
ms.assetid: d3dd52de-6d28-4d71-9b64-ba79e17bd9ee
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_e416cff1-5cad-4488-a3e2-ea0b42a7cd81.xml, D3DDDIARG_SETPRIORITY structure [Display Devices], _D3DDDIARG_SETPRIORITY, D3DDDIARG_SETPRIORITY, display.d3dddiarg_setpriority, d3dumddi/D3DDDIARG_SETPRIORITY
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
-	D3DDDIARG_SETPRIORITY
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETPRIORITY
---

# _D3DDDIARG_SETPRIORITY structure


## -description


The D3DDDIARG_SETPRIORITY structure describes the priority level to set for a managed texture. 


## -syntax


````
typedef struct _D3DDDIARG_SETPRIORITY {
  HANDLE hResource;
  UINT   Priority;
} D3DDDIARG_SETPRIORITY;
````


## -struct-fields




### -field hResource

A handle to the resource that contains the texture.


### -field Priority

The priority level to set for the texture that is contained in the <b>hResource</b> resource. A texture's priority value can be set anywhere in the range from 0 through 0xFFFFFFFF.


## -remarks



The driver receives only priority notifications for driver-managed textures.

The priority level at which a texture is set determines its eviction order from memory. A texture that is assigned a low priority is evicted before a texture with a high priority. If two textures have the same priority, the texture that was used more recently is kept in memory; the other texture is evicted. 




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpriority.md">SetPriority</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETPRIORITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

