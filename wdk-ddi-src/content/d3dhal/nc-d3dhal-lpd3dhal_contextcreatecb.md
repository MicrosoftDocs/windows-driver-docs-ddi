---
UID: NC:d3dhal.LPD3DHAL_CONTEXTCREATECB
title: LPD3DHAL_CONTEXTCREATECB
author: windows-driver-content
description: The D3dContextCreate function creates a context.
old-location: display\d3dcontextcreate.htm
old-project: display
ms.assetid: c960c3f4-7565-4163-b8c2-a13643110c8c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3dContextCreate, D3dContextCreate callback function [Display Devices], LPD3DHAL_CONTEXTCREATECB, LPD3DHAL_CONTEXTCREATECB callback, d3dfncs_d126e9ed-3783-4cc1-8fd6-34592b95bec7.xml, d3dhal/D3dContextCreate, display.d3dcontextcreate
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3dContextCreate
product: Windows
targetos: Windows
req.typenames: 
---

# LPD3DHAL_CONTEXTCREATECB callback function


## -description


The <b>D3dContextCreate</b> function creates a context.


## -parameters




### -param Arg1








#### - pccd [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a> structure that contains the information required to create a context and the data that the driver should store in the new context.


## -returns



<b>D3dContextCreate</b> returns one of the following callback codes:




## -remarks



<b>D3dContextCreate</b> must be implemented in drivers that support Microsoft Direct3D. It should perform the following steps:

<ul>
<li>
Initialize the driver's context with all information required by the driver to perform rendering. This includes associating the rendering target and depth buffer that the <b>lpDDSLcl</b> and <b>lpDDSZLcl</b> members of the D3DHAL_CONTEXTCREATEDATA structure at <b>pccd</b> point to, respectively, with the context.

</li>
<li>
Generate a unique context ID for this new context and return it in the <b>dwhContext</b> member of D3DHAL_CONTEXTCREATEDATA. Direct3D uses this context ID in every subsequent callback it makes to this Direct3D device. The driver must never create a context handle of zero.

</li>
<li>
Set the <b>ddrval</b> member of D3DHAL_CONTEXTCREATEDATA to DD_OK upon success, and to D3DHAL_OUTOFCONTEXTS if it cannot create the context.

</li>
<li>
Return DDHAL_DRIVER_HANDLED.

</li>
</ul>
<b>D3dContextCreate</b> should not cache the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a> structure that was passed in as the <b>lpDDLcl</b> member of D3DHAL_CONTEXTCREATEDATA. If the driver subsequently requires any information that is accessed through this DD_DIRECTDRAW_LOCAL pointer, the driver should store the information in the driver's private context data structure.

State is not shared between contexts; therefore, the driver must maintain full state information for each context. This state is changed by any subsequent calls to <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.

The driver must be able to reference all texture handles that are created within a context. The driver can then clean up all driver-specific data related to textures created within this context when a <a href="https://msdn.microsoft.com/caed780c-06a1-4697-b102-bffb134ecf84">D3dContextDestroy</a> call is made. 

<b>D3dContextCreate</b> can be called with a disabled <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDEV</a>. A PDEV is disabled or enabled by calling the display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a> function. See <a href="https://msdn.microsoft.com/f7badbe8-b24f-438a-8937-95bb98de6310">Managing PDEVs</a> for more information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a>



<a href="https://msdn.microsoft.com/caed780c-06a1-4697-b102-bffb134ecf84">D3dContextDestroy</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a>
 

 

