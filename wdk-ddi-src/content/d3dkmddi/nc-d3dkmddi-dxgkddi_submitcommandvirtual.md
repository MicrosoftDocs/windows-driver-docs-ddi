---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMANDVIRTUAL
title: DXGKDDI_SUBMITCOMMANDVIRTUAL
author: windows-driver-content
description: DxgkDdiSubmitCommandVirtual is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing.
old-location: display\dxgkddisubmitcommandvirtual.htm
ms.assetid: 7A55FB51-BDC2-4215-895E-3250579BEAF0
ms.date: 5/10/2018
ms.keywords: DXGKDDI_SUBMITCOMMANDVIRTUAL, DXGKDDI_SUBMITCOMMANDVIRTUAL callback, DxgkDdiSubmitCommandVirtual, DxgkDdiSubmitCommandVirtual callback function [Display Devices], d3dkmddi/DxgkDdiSubmitCommandVirtual, display.dxgkddisubmitcommandvirtual
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
-	DxgkDdiSubmitCommandVirtual
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SUBMITCOMMANDVIRTUAL callback function


## -description


<b>DxgkDdiSubmitCommandVirtual</b> is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing.



The driver is responsible for making sure the correct address space is restored ahead of submitting a particular DMA buffer.
  


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. 


### -param pSubmitCommand [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906825">DXGKARG_SUBMITCOMMANDVIRTUAL</a> structure that describes operation.


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
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The DMA or private data is determined to be malformed. In this case, the OS will put the calling device in an error state and all subsequent calls on it will fail. The <b>SubmissionFenceId</b> value passed to this call will be considered completed after all previous packets on the hardware finished and at that point the driver notion of the last completed fence ID should be updated to this value.

<div class="alert"><b>Note</b>  This behavior is different from <a href="https://msdn.microsoft.com/de1925ab-e444-4cf6-acd9-8fdab26afcec">DxgkDdiSubmitCommand</a> call where no error is allowed to be returned due to the ability to validate the data in a prior <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> call.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt></dt>
</dl>
</td>
<td width="60%">
All other return values will lead to the OS <i>bugcheck</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906825">DXGKARG_SUBMITCOMMANDVIRTUAL</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>



<a href="https://msdn.microsoft.com/de1925ab-e444-4cf6-acd9-8fdab26afcec">DxgkDdiSubmitCommand</a>
 

 

