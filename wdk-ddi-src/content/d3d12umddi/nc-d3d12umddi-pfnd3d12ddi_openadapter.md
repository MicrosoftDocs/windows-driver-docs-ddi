---
UID: NC:d3d12umddi.PFND3D12DDI_OPENADAPTER
title: PFND3D12DDI_OPENADAPTER
author: windows-driver-content
description: The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\pfnd3d12ddi_openadapter.htm
ms.assetid: FEDC2FB5-9F1A-4829-A98D-3BEA4218AE3D
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_OPENADAPTER, PFND3D12DDI_OPENADAPTER callback, PFND3D12DDI_OPENADAPTER callback function [Display Devices], d3d12umddi/PFND3D12DDI_OPENADAPTER, display.pfnd3d12ddi_openadapter
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
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
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_OPENADAPTER
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_OPENADAPTER callback function


## -description


The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls. 


## -parameters




### -param *


A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt779069">D3D12DDIARG_OPENADAPTER</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.



## -returns




             PFND3D12DDI_OPENADAPTER returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

                PFND3D12DDI_OPENADAPTER could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 




## -remarks



The graphics adapter object that is created by the PFND3D12DDI_OPENADAPTER function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt779070">PFND3D12DDI_CREATEDEVICE_0003</a>, the user-mode display driver should call the <a href="https://msdn.microsoft.com/8008574f-a89e-4fed-b745-7cf5baa68e64">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.



