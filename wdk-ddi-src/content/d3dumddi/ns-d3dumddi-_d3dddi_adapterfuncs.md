---
UID: NS:d3dumddi._D3DDDI_ADAPTERFUNCS
title: "_D3DDDI_ADAPTERFUNCS"
author: windows-driver-content
description: The D3DDDI_ADAPTERFUNCS structure contains functions that the user-mode display driver can implement to communicate with a graphics adapter object.
old-location: display\d3dddi_adapterfuncs.htm
old-project: display
ms.assetid: bbf4852c-0fa5-47c0-a77e-7114b2a77549
ms.author: windowsdriverdev
ms.date: 3/29/2018
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


## -struct-fields




### -field pfnGetCaps

A pointer to the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function that queries for capabilities of the graphics hardware.


### -field pfnCreateDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> function that creates a representation of a display device that handles a collection of rendering state.


### -field pfnCloseAdapter

A pointer to the driver's <a href="https://msdn.microsoft.com/9dc7f71a-753d-41ca-8eaa-bff6536e834f">CloseAdapter</a> function that releases resources for a graphics adapter object.


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




<a href="https://msdn.microsoft.com/9dc7f71a-753d-41ca-8eaa-bff6536e834f">CloseAdapter</a>



<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543226">D3DDDIARG_OPENADAPTER</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>



<a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a>
 

 

