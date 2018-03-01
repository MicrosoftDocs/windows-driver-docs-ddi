---
UID: NS:d3dumddi._D3DDDI_ADAPTERFUNCS
title: "_D3DDDI_ADAPTERFUNCS"
author: windows-driver-content
description: The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3dddi_adapterfuncs.htm
old-project: display
ms.assetid: bbf4852c-0fa5-47c0-a77e-7114b2a77549
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_ADAPTERFUNCS, D3DDDI_ADAPTERFUNCS structure [Display Devices], D3D_other_Structs_2397321f-704c-4c93-bbd1-b7591134294c.xml, _D3DDDI_ADAPTERFUNCS, d3dumddi/D3DDDI_ADAPTERFUNCS, display.d3dddi_adapterfuncs
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
-	D3DDDI_ADAPTERFUNCS
product: Windows
targetos: Windows
req.typenames: D3DDDI_ADAPTERFUNCS
---

# _D3DDDI_ADAPTERFUNCS structure


## -description


The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object. 


## -syntax


````
typedef struct _D3DDDI_ADAPTERFUNCS {
  PFND3DDDI_GETCAPS      pfnGetCaps;
  PFND3DDDI_CREATEDEVICE pfnCreateDevice;
  PFND3DDDI_CLOSEADAPTER pfnCloseAdapter;
} D3DDDI_ADAPTERFUNCS;
````


## -struct-fields




### -field pfnGetCaps

A pointer to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function that queries for capabilities of the graphics hardware.


### -field pfnCreateDevice

A pointer to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> function that creates a representation of a display device that handles a collection of rendering state.


### -field pfnCloseAdapter

A pointer to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_closeadapter.md">CloseAdapter</a> function that releases resources for a graphics adapter object.


## -remarks



Multiple graphics adapter objects can be created for a single physical graphics adapter.

The following code example demonstrates the function declarations for the functions that the members of D3DDDI_ADAPTERFUNCS point to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef HRESULT (APIENTRY *PFND3DDDI_GETCAPS)(HANDLE hAdapter, CONST D3DDDIARG_GETCAPS*);
typedef HRESULT (APIENTRY *PFND3DDDI_CREATEDEVICE)(IN HANDLE hAdapter, IN D3DDDIARG_CREATEDEVICE*);
typedef HRESULT (APIENTRY *PFND3DDDI_CLOSEADAPTER)(IN HANDLE hAdapter);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_openadapter.md">D3DDDIARG_OPENADAPTER</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_closeadapter.md">CloseAdapter</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_ADAPTERFUNCS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

