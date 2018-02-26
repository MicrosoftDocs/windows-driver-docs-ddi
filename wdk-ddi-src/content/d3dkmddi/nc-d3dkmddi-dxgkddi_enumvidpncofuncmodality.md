---
UID: NC:d3dkmddi.DXGKDDI_ENUMVIDPNCOFUNCMODALITY
title: DXGKDDI_ENUMVIDPNCOFUNCMODALITY
author: windows-driver-content
description: The DxgkDdiEnumVidPnCofuncModality function makes the source and target modes sets of a VidPN cofunctional with the VidPN's topology and the modes that have already been pinned.
old-location: display\dxgkddienumvidpncofuncmodality.htm
old-project: display
ms.assetid: 6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_ENUMVIDPNCOFUNCMODALITY, DmFunctions_e8c49ebf-a4af-4a36-a32b-0ab6874e660a.xml, DxgkDdiEnumVidPnCofuncModality, DxgkDdiEnumVidPnCofuncModality callback function [Display Devices], d3dkmddi/DxgkDdiEnumVidPnCofuncModality, display.dxgkddienumvidpncofuncmodality
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
-	DxgkDdiEnumVidPnCofuncModality
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_ENUMVIDPNCOFUNCMODALITY callback


## -description


The <i>DxgkDdiEnumVidPnCofuncModality</i> function makes the source and target modes sets of a VidPN cofunctional with the VidPN's topology and the modes that have already been pinned.


## -prototype


````
DXGKDDI_ENUMVIDPNCOFUNCMODALITY DxgkDdiEnumVidPnCofuncModality;

NTSTATUS APIENTRY DxgkDdiEnumVidPnCofuncModality(
  _In_ const HANDLE                                hAdapter,
  _In_ const DXGKARG_ENUMVIDPNCOFUNCMODALITY CONST *pEnumCofuncModalityArg
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pEnumCofuncModality








#### - pEnumCofuncModalityArg [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_enumvidpncofuncmodality.md">DXGKARG_ENUMVIDPNCOFUNCMODALITY</a> structure that contains function arguments.


## -returns



<i>DxgkDdiEnumVidPnCofuncModality</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The <b>hConstrainingVidPn</b> member of <i>pEnumCofuncModalityArg</i> is a handle to a VidPN object called the constraining VidPN. Other members of <i>pEnumCofuncModalityArg</i> identify one video present source or target as the pivot of the enumeration (or specify that there is no pivot). 

<i>DxgkDdiEnumVidPnCofuncModality</i> must perform the following tasks:

<ul>
<li>
Examine the topology and mode sets of the constraining VidPN.

</li>
<li>
Update each mode set that is not the pivot and does not already have a pinned mode. The updated mode sets must be cofunctional with the VidPN's topology and with any modes that have already been pinned.

</li>
</ul>
Note that if a source or target is identified as the pivot of the enumeration, the mode set for that source or target must not change. For more information about how to update source and target mode sets, see <a href="https://msdn.microsoft.com/f1aa6277-7af6-4ba0-8ff1-d562f7029540">Enumerating Cofunctional VidPN Source and Target Modes</a>. 

The <i>DxgkDdiEnumVidPnCofuncModality</i> function should be made pageable.



