---
UID: NS:d3dumddi._D3DDDIARG_DESTROYAUTHENICATEDCHANNEL
title: "_D3DDDIARG_DESTROYAUTHENICATEDCHANNEL"
author: windows-driver-content
description: The D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure contains the handle to an authenticated channel that is destroyed in a call to the DestroyAuthenticatedChannel function.
old-location: display\d3dddiarg_destroyauthenticatedchannel.htm
old-project: display
ms.assetid: 3b953c73-a033-465a-a041-7c21ee307c32
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL, D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure [Display Devices], E, G, H, I, L, N, O, R, S, T, U, UMDisplayDriver_param_Structs_be6187b3-2d01-450e-90a7-d01a97aba764.xml, Y, _, _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL, display.d3dddiarg_destroyauthenticatedchannel"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL structure


## -description


The D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure contains the handle to an authenticated channel that is destroyed in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a> function. 


## -syntax


````
typedef struct _D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL {
  HANDLE hChannel;
} D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL;
````


## -struct-fields




### -field hChannel

[in] The handle to the authenticated channel that the driver destroys.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

