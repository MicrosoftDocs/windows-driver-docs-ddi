---
UID: NS:d3dumddi._D3DDDI_ADAPTERCALLBACKS
title: "_D3DDDI_ADAPTERCALLBACKS"
author: windows-driver-content
description: The D3DDDI_ADAPTERCALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.
old-location: display\d3dddi_adaptercallbacks.htm
tech.root: display
ms.assetid: b912449b-45d1-473d-aa14-b3f3ffbfefff
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDI_ADAPTERCALLBACKS, D3DDDI_ADAPTERCALLBACKS structure [Display Devices], D3D_other_Structs_6919397d-68ab-4ada-9f39-bf08bc0ac9ae.xml, _D3DDDI_ADAPTERCALLBACKS, d3dumddi/D3DDDI_ADAPTERCALLBACKS, display.d3dddi_adaptercallbacks
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
-	D3DDDI_ADAPTERCALLBACKS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_ADAPTERCALLBACKS
---

# _D3DDDI_ADAPTERCALLBACKS structure


## -description


The D3DDDI_ADAPTERCALLBACKS structure contains Microsoft Direct3D runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnQueryAdapterInfoCb

A pointer to the <a href="https://msdn.microsoft.com/8008574f-a89e-4fed-b745-7cf5baa68e64">pfnQueryAdapterInfoCb</a> function, which the user-mode display driver uses to query the display miniport driver for adapter configuration information.


### -field pfnGetMultisampleMethodListCb

A pointer to the <a href="https://msdn.microsoft.com/2e3f9ee9-83a0-4b81-a22b-594e5bd4d046">pfnGetMultisampleMethodListCb</a> function, which the user-mode display driver uses to retrieve the list of multiple-sampling methods that are used for an allocation.

### -field pfnQueryAdapterInfoCb2

## -remarks



The following code example demonstrates the function declarations for the functions that the members of D3DDDI_ADAPTERCALLBACKS point to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef HRESULT (APIENTRY CALLBACK *PFND3DDDI_QUERYADAPTERINFOCB)(HANDLE hAdapter, CONST D3DDDICB_QUERYADAPTERINFO*);
typedef HRESULT (APIENTRY CALLBACK *PFND3DDDI_GETMULTISAMPLEMETHODLISTCB)(HANDLE hAdapter, D3DDDICB_GETMULTISAMPLEMETHODLIST*);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543226">D3DDDIARG_OPENADAPTER</a>



<a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a>



<a href="https://msdn.microsoft.com/2e3f9ee9-83a0-4b81-a22b-594e5bd4d046">pfnGetMultisampleMethodListCb</a>



<a href="https://msdn.microsoft.com/8008574f-a89e-4fed-b745-7cf5baa68e64">pfnQueryAdapterInfoCb</a>
 

 

