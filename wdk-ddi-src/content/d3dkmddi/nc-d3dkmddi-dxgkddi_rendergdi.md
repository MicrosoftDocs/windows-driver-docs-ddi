---
UID: NC:d3dkmddi.DXGKDDI_RENDERGDI
title: DXGKDDI_RENDERGDI
author: windows-driver-content
description: DxgkDdiRenderGdi is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.
old-location: display\dxgkddirendergdi.htm
ms.assetid: 90C34125-FC32-46E3-81F7-6B2AACED9BAC
ms.date: 05/10/2018
ms.keywords: DXGKDDI_RENDERGDI, DXGKDDI_RENDERGDI callback, DxgkDdiRenderGdi, DxgkDdiRenderGdi callback function [Display Devices], d3dkmddi/DxgkDdiRenderGdi, display.dxgkddirendergdi
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmddi.h
api_name:
-	DxgkDdiRenderGdi
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_RENDERGDI callback function


## -description


<b>DxgkDdiRenderGdi</b> is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.


## -parameters




### -param hContext [in]

A handle to a context block that is associated with a display adapter. 


### -param pRenderGdi [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906823">DXGKARG_RENDERGDI</a> structure that describes operation.


## -returns



<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>
</td>
<td width="60%">
The submitted command is well-formed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>(other)</dt>
</dl>
</td>
<td width="60%">
All other return values will lead to the OS <i>bugcheck</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906823">DXGKARG_RENDERGDI</a>
 

 

