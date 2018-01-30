---
UID: NC:d3dhal.LPD3DHAL_CONTEXTCREATECB
title: LPD3DHAL_CONTEXTCREATECB
author: windows-driver-content
description: The D3dContextCreate function creates a context.
old-location: display\d3dcontextcreate.htm
old-project: display
ms.assetid: c960c3f4-7565-4163-b8c2-a13643110c8c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dcontextcreate, D3dContextCreate callback function [Display Devices], D3dContextCreate, LPD3DHAL_CONTEXTCREATECB, LPD3DHAL_CONTEXTCREATECB, d3dhal/D3dContextCreate, d3dfncs_d126e9ed-3783-4cc1-8fd6-34592b95bec7.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dhal.h
apiname:
-	D3dContextCreate
product: Windows
targetos: Windows
req.typenames: D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS
---

# LPD3DHAL_CONTEXTCREATECB callback


## -description


The <b>D3dContextCreate</b> function creates a context.


## -prototype


````
LPD3DHAL_CONTEXTCREATECB D3dContextCreate;

DWORD APIENTRY D3dContextCreate(
  _In_ LPD3DHAL_CONTEXTCREATEDATA pccd
)
{ ... }
````


## -parameters




### -param LPD3DHAL_CONTEXTCREATEDATA






#### - pccd [in]

Points to a <a href="..\d3dhal\ns-d3dhal-_d3dhal_contextcreatedata.md">D3DHAL_CONTEXTCREATEDATA</a> structure that contains the information required to create a context and the data that the driver should store in the new context.


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
</ul><b>D3dContextCreate</b> should not cache the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a> structure that was passed in as the <b>lpDDLcl</b> member of D3DHAL_CONTEXTCREATEDATA. If the driver subsequently requires any information that is accessed through this DD_DIRECTDRAW_LOCAL pointer, the driver should store the information in the driver's private context data structure.

State is not shared between contexts; therefore, the driver must maintain full state information for each context. This state is changed by any subsequent calls to <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.

The driver must be able to reference all texture handles that are created within a context. The driver can then clean up all driver-specific data related to textures created within this context when a <a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextdestroycb.md">D3dContextDestroy</a> call is made. 

<b>D3dContextCreate</b> can be called with a disabled <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDEV</a>. A PDEV is disabled or enabled by calling the display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a> function. See <a href="https://msdn.microsoft.com/f7badbe8-b24f-438a-8937-95bb98de6310">Managing PDEVs</a> for more information. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a>

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_contextdestroycb.md">D3dContextDestroy</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_contextcreatedata.md">D3DHAL_CONTEXTCREATEDATA</a>

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20LPD3DHAL_CONTEXTCREATECB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

