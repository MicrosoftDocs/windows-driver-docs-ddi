---
UID: NC:d3dhal.LPD3DHAL_CONTEXTDESTROYCB
title: LPD3DHAL_CONTEXTDESTROYCB (d3dhal.h)
description: The D3dContextDestroy function deletes the specified context.
old-location: display\d3dcontextdestroy.htm
tech.root: display
ms.assetid: caed780c-06a1-4697-b102-bffb134ecf84
ms.date: 05/10/2018
ms.keywords: D3dContextDestroy, D3dContextDestroy callback function [Display Devices], LPD3DHAL_CONTEXTDESTROYCB, LPD3DHAL_CONTEXTDESTROYCB callback, d3dfncs_95c72dbe-9292-4501-ae28-f76316ce01e5.xml, d3dhal/D3dContextDestroy, display.d3dcontextdestroy
ms.topic: callback
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3dContextDestroy
product:
- Windows
targetos: Windows
req.typenames: 
---

# LPD3DHAL_CONTEXTDESTROYCB callback function


## -description


The <b>D3dContextDestroy</b> function deletes the specified context.


## -parameters




### -param Arg1

*pcdd* [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544748">D3DHAL_CONTEXTDESTROYDATA</a> structure that contains the information required for the driver to destroy the context. 


## -returns



<b>D3dContextDestroy</b> returns one of the following callback codes:




## -remarks



All Microsoft Direct3D drivers must support <b>D3dContextDestroy</b>.

The driver should free all resources it allocated to the context that is being deleted. For example, the driver should free the following resources it associated with the context: 

<ul>
<li>
Texture resources

</li>
<li>
Vertex and pixel <a href="https://msdn.microsoft.com/23b38ffb-ce15-4e61-bf7f-7f71848e077f">shaders</a>


</li>
<li>

<a href="https://msdn.microsoft.com/6da26a8f-553b-4995-9dda-66a7fd6d478b">Declarations and code for vertex shaders</a>


</li>
<li>
Resources for <a href="https://msdn.microsoft.com/fe7dff3b-8941-4ab1-9539-0be9b59af5e6">asynchronous queries</a>


</li>
</ul>
The driver should not free the Microsoft DirectDraw surfaces associated with the context because these will be freed by DirectDraw in response to an application or Direct3D runtime request.

If the driver cached the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a> structure that was passed in as the <b>lpDDLcl</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a> structure when <a href="https://msdn.microsoft.com/c960c3f4-7565-4163-b8c2-a13643110c8c">D3dContextCreate</a> was called, the pointer might become invalid before <b>D3dContextDestroy</b> is called. Therefore, <b>D3dContextDestroy</b> must not dereference this DD_DIRECTDRAW_LOCAL pointer because an access violation might result or random data might be returned. For example, if the driver's <a href="https://msdn.microsoft.com/c68b924b-422d-4a01-8dac-674835833798">D3dDestroyDDLocal</a> function is called before <b>D3dContextDestroy</b>, the operating system releases this DD_DIRECTDRAW_LOCAL pointer before the <b>D3dContextDestroy</b> call.

<b>D3dContextDestroy</b> can be called with a disabled <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDEV</a>. A PDEV is disabled or enabled by calling the display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a> function. See <a href="https://msdn.microsoft.com/f7badbe8-b24f-438a-8937-95bb98de6310">Managing PDEVs</a> for more information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544748">D3DHAL_CONTEXTDESTROYDATA</a>



<a href="https://msdn.microsoft.com/c960c3f4-7565-4163-b8c2-a13643110c8c">D3dContextCreate</a>



<a href="https://msdn.microsoft.com/c68b924b-422d-4a01-8dac-674835833798">D3dDestroyDDLocal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a>
 

 

