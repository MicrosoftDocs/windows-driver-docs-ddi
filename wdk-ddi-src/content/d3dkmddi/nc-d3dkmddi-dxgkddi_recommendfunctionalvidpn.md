---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDFUNCTIONALVIDPN
title: DXGKDDI_RECOMMENDFUNCTIONALVIDPN
author: windows-driver-content
description: The DxgkDdiRecommendFunctionalVidPn function creates a functional VidPN that can be implemented on a specified display adapter.
old-location: display\dxgkddirecommendfunctionalvidpn.htm
old-project: display
ms.assetid: 320a77a7-d7d4-47b9-8a40-2b6e12819e4b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddirecommendfunctionalvidpn, DxgkDdiRecommendFunctionalVidPn callback function [Display Devices], DxgkDdiRecommendFunctionalVidPn, DXGKDDI_RECOMMENDFUNCTIONALVIDPN, DXGKDDI_RECOMMENDFUNCTIONALVIDPN, d3dkmddi/DxgkDdiRecommendFunctionalVidPn, DmFunctions_9b5062a8-31fa-4351-bf10-a90f57bbaed8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiRecommendFunctionalVidPn
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_RECOMMENDFUNCTIONALVIDPN callback


## -description


The <i>DxgkDdiRecommendFunctionalVidPn</i> function creates a functional VidPN that can be implemented on a specified display adapter.


## -prototype


````
DXGKDDI_RECOMMENDFUNCTIONALVIDPN DxgkDdiRecommendFunctionalVidPn;

NTSTATUS APIENTRY DxgkDdiRecommendFunctionalVidPn(
  _In_ const HANDLE                                 hAdapter,
  _In_ const DXGKARG_RECOMMENDFUNCTIONALVIDPN CONST *pRecommendFunctionalVidPnArg
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pRecommendFunctionalVidPn






#### - pRecommendFunctionalVidPnArg [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_recommendfunctionalvidpn.md">DXGKARG_RECOMMENDFUNCTIONALVIDPN</a> structure that contains function arguments. The caller supplies the <b>hRecommendedFunctionalVidPn</b> member, which is a handle to an empty VidPN object. <i>DxgkDdiRecommendFunctionalVidPn</i> populates the VidPN object with the elements of a functional VidPN: topology, mode sets, pinned modes.


## -returns


<i>DxgkDdiRecommendFunctionalVidPn </i>returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded in creating a functional VidPN.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NO_RECOMMENDED_FUNCTIONAL_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The function was not able to create a functional VidPN.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The function failed because it was unable to allocate memory.

</td>
</tr>
</table> 



## -remarks


A VidPN is functional if it satisfies the following conditions:
<ul>
<li>
It has a topology that has at least one path. (A path is an association between a source and a target.)

</li>
<li>
Every source and target in the topology has a pinned mode.

</li>
</ul>The job of <i>DxgkDdiRecommendFunctionalVidPn</i> is to create a functional VidPN that can be implemented on the display adapter. The following list gives the steps used to create a functional VidPN.
<ol>
<li>
Start with a handle to an empty VidPN object. This handle was supplied in the <b>hDesiredVidPn</b> member of <i>pRecommendFunctionalVidPnArg.</i>

</li>
<li>
Add a path (source-target pair) to the topology of the VidPN.

</li>
<li>
Create a new source mode set and add one source mode to the set. Assign the source mode set to the source in your path. Pin the source mode. 

</li>
<li>
Create a new target mode set and add one target mode to the set. Assign the target mode set to the target in your path. Pin the target mode.

</li>
</ol>For information about how to add paths, add mode sets, assign modes, and pin modes, see <a href="https://msdn.microsoft.com/5dedac8c-9a99-4b3a-81be-39819135cd97">VidPN Objects and Interfaces</a>.

<i>DxgkDdiRecommendFunctionalVidPn</i> should be made pageable.


