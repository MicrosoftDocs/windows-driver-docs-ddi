---
UID: NC:d3dumddi.PFND3DDDI_DELETEVERTEXSHADERDECL
title: PFND3DDDI_DELETEVERTEXSHADERDECL
author: windows-driver-content
description: The DeleteVertexShaderDecl function cleans up driver-side resources that are associated with the vertex shader declaration.
old-location: display\deletevertexshaderdecl.htm
old-project: display
ms.assetid: 8c16cd27-83f9-4474-9031-edfea0ba665b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DeleteVertexShaderDecl, DeleteVertexShaderDecl callback function [Display Devices], PFND3DDDI_DELETEVERTEXSHADERDECL, UserModeDisplayDriver_Functions_b62ed121-1403-4a6e-8854-6f2dfba6fac6.xml, d3dumddi/DeleteVertexShaderDecl, display.deletevertexshaderdecl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DeleteVertexShaderDecl
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DELETEVERTEXSHADERDECL callback


## -description


The <b>DeleteVertexShaderDecl</b> function cleans up driver-side resources that are associated with the vertex shader declaration.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param Arg1








#### - hShaderHandle [in]

 A handle to the vertex shader declaration object.


## -returns



<b>DeleteVertexShaderDecl</b> returns S_OK or an appropriate error result if the vertex shader declaration object is not successfully cleaned up.




## -remarks



The <b>DeleteVertexShaderDecl</b> function notifies the driver about the deletion of the vertex shader declaration object that the <a href="https://msdn.microsoft.com/00c53e81-93db-46b8-b65c-c8d62059452a">CreateVertexShaderDecl</a> function created. The driver can then clean up any driver-side resources that are associated with the vertex shader declaration.




## -see-also




<a href="https://msdn.microsoft.com/00c53e81-93db-46b8-b65c-c8d62059452a">CreateVertexShaderDecl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

