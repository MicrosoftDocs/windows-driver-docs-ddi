---
UID: NC:d3dkmddi.DXGKDDI_SETPOINTERSHAPE
title: DXGKDDI_SETPOINTERSHAPE
author: windows-driver-content
description: The DxgkDdiSetPointerShape function sets the appearance and location of the mouse pointer.
old-location: display\dxgkddisetpointershape.htm
ms.assetid: 36b462f7-5bad-4716-8138-af00d20e945b
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETPOINTERSHAPE, DXGKDDI_SETPOINTERSHAPE callback, DmFunctions_39ac69a2-f8dc-4704-b5ab-d57d83685071.xml, DxgkDdiSetPointerShape, DxgkDdiSetPointerShape callback function [Display Devices], d3dkmddi/DxgkDdiSetPointerShape, display.dxgkddisetpointershape
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiSetPointerShape
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETPOINTERSHAPE callback function


## -description


The <i>DxgkDdiSetPointerShape</i> function sets the appearance and location of the mouse pointer.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pSetPointerShape [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559481">DXGKARG_SETPOINTERSHAPE</a> structure that describes the appearance and location of the mouse pointer.


## -returns



<i>DxgkDdiSetPointerShape</i> returns one of the following values:

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
The mouse pointer is successfully drawn.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiSetPointerShape</i> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiSetPointerShape</i> function to set information about the mouse pointer. The <i>DxgkDdiSetPointerShape</i> function is called independently of all of the other display miniport driver functions. Therefore, a <i>DxgkDdiSetPointerShape</i> thread can run simultaneously with another display miniport driver thread. However, the system ensures that <i>DxgkDdiSetPointerShape</i> and <a href="https://msdn.microsoft.com/b30e4f19-068c-4ab0-a2e9-b1f57592be1c">DxgkDdiSetPointerPosition</a> threads cannot run simultaneously. 

If you run a <i>DxgkDdiSetPointerShape</i> thread simultaneously with another display miniport driver thread, the display miniport driver should be able to program the mouse pointer hardware independently of other activities, such as operations that send a command buffer through direct memory access (DMA) to the graphics hardware, operations that program the graphics hardware by using memory-mapped I/O (MMIO), and so on.

<i>DxgkDdiSetPointerShape</i> is not called if the video present network (VidPN) topology that is associated with the <b>VidPnSourceId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559481">DXGKARG_SETPOINTERSHAPE</a> structure that the <i>pSetPointerShape</i> parameter points to is disabled.

<i>DxgkDdiSetPointerShape</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559481">DXGKARG_SETPOINTERSHAPE</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/b30e4f19-068c-4ab0-a2e9-b1f57592be1c">DxgkDdiSetPointerPosition</a>
 

 

