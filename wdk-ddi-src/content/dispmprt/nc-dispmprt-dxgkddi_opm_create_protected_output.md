---
UID: NC:dispmprt.DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT
title: DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT
author: windows-driver-content
description: The DxgkDdiOPMCreateProtectedOutput function creates a new protected output object with Certified Output Protection Protocol (COPP) or OPM semantics.
old-location: display\dxgkddiopmcreateprotectedoutput.htm
old-project: display
ms.assetid: 8143732e-cef6-49f1-9b20-db6b6ee073e6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT, Dm_Opm_functions_207f1385-efcc-4c5c-8237-e07f594c9742.xml, DxgkDdiOPMCreateProtectedOutput, DxgkDdiOPMCreateProtectedOutput callback function [Display Devices], display.dxgkddiopmcreateprotectedoutput, dispmprt/DxgkDdiOPMCreateProtectedOutput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiOPMCreateProtectedOutput
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT callback


## -description


The<i> DxgkDdiOPMCreateProtectedOutput</i> function creates a new protected output object with Certified Output Protection Protocol (COPP) or OPM semantics.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param VidPnTargetId [in]

An integer that uniquely identifies the video present target that corresponds to the new protected output object. Each video present target must correspond to one physical monitor connector. If <i>VidPnTargetId</i> corresponds to multiple physical monitor connectors, <i>DxgkDdiOPMCreateProtectedOutput</i> should return the STATUS_GRAPHICS_OPM_SPANNING_MODE_ENABLED or STATUS_GRAPHICS_OPM_THEATER_MODE_ENABLED error code. 


### -param NewVideoOutputSemantics [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560933">DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS</a>-typed value that determines whether the new protected output has COPP or OPM semantics.


### -param NewProtectedOutputHandle [out]

A pointer to a variable that receives the handle to the new protected output object if <i>DxgkDdiOPMCreateProtectedOutput</i> returns successfully. The DirectX graphics kernel subsystem passes this handle in calls to the display miniport driver's <a href="https://msdn.microsoft.com/91b07a5c-ed25-4268-bd6d-273ae8b1ac28">DxgkDdiOPMGetRandomNumber</a>, <a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>, <a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>, <a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>, and <a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMDestroyProtectedOutput</a>.

If <i>DxgkDdiOPMCreateProtectedOutput</i> fails, the value of the variable is unchanged.


## -returns



<i>DxgkDdiOPMCreateProtectedOutput</i> returns one of the following values.

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
The function successfully created a new protected output object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_OPM_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support OPM either because the hardware vender never signed the OPM license agreement or the miniport driver's graphics hardware does not comply with OPM rules. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_COPP_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support COPP either because the hardware vender never signed the COPP license agreement or the miniport driver's graphics hardware does not comply with COPP rules. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiOPMCreateProtectedOutput</i> cannot allocate memory required for it to complete. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_OPM_SPANNING_MODE_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiOPMCreateProtectedOutput</i> could not create a protected output because the video present target is in spanning mode. When the video present target is in spanning mode, it corresponds to multiple physical monitor connectors and each connector displays a separate part of the frame buffer. For a diagram of how the display miniport driver typically implements spanning mode, see the Remarks section. 

The display miniport driver informs the operating system on how the frame buffer corresponds to a particular monitor. The left half of the frame buffer is displayed on one monitor, and the right half of the frame buffer is displayed on the other monitor. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_OPM_THEATER_MODE_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiOPMCreateProtectedOutput</i> could not create a protected output because the video present target is in theater mode. When the video present target is in theater mode, it corresponds to two physical monitor connectors; one connector displays the entire frame buffer and the other connector displays only part of the frame buffer. Theater mode is also known as mirror mode. For a diagram of how the display miniport driver typically implements theater mode, see the Remarks section. 

The display miniport driver informs the operating system on how the frame buffer corresponds to a particular monitor. The entire frame buffer is displayed on one monitor, and only part of the frame buffer is displayed on the other monitor. 

</td>
</tr>
</table>
 

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



The following figure shows how the display miniport driver typically implements spanning mode.

<img alt="Diagram illustrating spanning mode" src="images/opm_span.png"/>
The following figure shows how the display miniport driver typically implements theater mode.

<img alt="Diagram illustrating theater mode" src="images/opm_theater.png"/>
<i>DxgkDdiOPMCreateProtectedOutput</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560933">DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/a03381ba-342e-409f-99ab-9790e1d74371">DxgkDdiOPMDestroyProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>



<a href="https://msdn.microsoft.com/91b07a5c-ed25-4268-bd6d-273ae8b1ac28">DxgkDdiOPMGetRandomNumber</a>



<a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
 

 

