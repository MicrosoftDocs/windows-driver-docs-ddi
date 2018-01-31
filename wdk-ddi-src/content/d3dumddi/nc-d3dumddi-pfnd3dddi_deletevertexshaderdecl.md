---
UID: NC:d3dumddi.PFND3DDDI_DELETEVERTEXSHADERDECL
title: PFND3DDDI_DELETEVERTEXSHADERDECL
author: windows-driver-content
description: The DeleteVertexShaderDecl function cleans up driver-side resources that are associated with the vertex shader declaration.
old-location: display\deletevertexshaderdecl.htm
old-project: display
ms.assetid: 8c16cd27-83f9-4474-9031-edfea0ba665b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.deletevertexshaderdecl, DeleteVertexShaderDecl callback function [Display Devices], DeleteVertexShaderDecl, PFND3DDDI_DELETEVERTEXSHADERDECL, PFND3DDDI_DELETEVERTEXSHADERDECL, d3dumddi/DeleteVertexShaderDecl, UserModeDisplayDriver_Functions_b62ed121-1403-4a6e-8854-6f2dfba6fac6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	DeleteVertexShaderDecl
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DELETEVERTEXSHADERDECL callback


## -description


The <b>DeleteVertexShaderDecl</b> function cleans up driver-side resources that are associated with the vertex shader declaration.


## -prototype


````
PFND3DDDI_DELETEVERTEXSHADERDECL DeleteVertexShaderDecl;

__checkReturn HRESULT APIENTRY DeleteVertexShaderDecl(
  _In_ HANDLE hDevice,
  _In_ HANDLE hShaderHandle
)
{ ... }
````


## -parameters




#### - hDevice [in]

 A handle to the display device (graphics context).


### -param HANDLE






#### - hShaderHandle [in]

 A handle to the vertex shader declaration object.


## -returns


<b>DeleteVertexShaderDecl</b> returns S_OK or an appropriate error result if the vertex shader declaration object is not successfully cleaned up.



## -remarks


The <b>DeleteVertexShaderDecl</b> function notifies the driver about the deletion of the vertex shader declaration object that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderdecl.md">CreateVertexShaderDecl</a> function created. The driver can then clean up any driver-side resources that are associated with the vertex shader declaration.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderdecl.md">CreateVertexShaderDecl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DELETEVERTEXSHADERDECL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

