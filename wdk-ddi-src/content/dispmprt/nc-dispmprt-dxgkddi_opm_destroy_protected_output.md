---
UID: NC:dispmprt.DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT
title: DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT (dispmprt.h)
description: The DxgkDdiOPMDestroyProtectedOutput function destroys the given protected output object.
old-location: display\dxgkddiopmdestroyprotectedoutput.htm
tech.root: display
ms.assetid: a03381ba-342e-409f-99ab-9790e1d74371
ms.date: 05/10/2018
keywords: ["DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT callback function"]
ms.keywords: DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT, DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT callback, Dm_Opm_functions_e744a9ff-d14b-4cef-aed6-4dba714dc695.xml, DxgkDdiOPMDestroyProtectedOutput, DxgkDdiOPMDestroyProtectedOutput callback function [Display Devices], display.dxgkddiopmdestroyprotectedoutput, dispmprt/DxgkDdiOPMDestroyProtectedOutput
f1_keywords:
 - "dispmprt/DxgkDdiOPMDestroyProtectedOutput"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiOPMDestroyProtectedOutput
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT callback function


## -description


The <i>DxgkDdiOPMDestroyProtectedOutput</i> function destroys the given protected output object.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


## -returns



<i>DxgkDdiOPMDestroyProtectedOutput</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. 

<div class="alert"><b>Note</b>  <i>DxgkDdiOPMDestroyProtectedOutput</i> cannot fail if the ProtectedOutputHandle parameter contains a valid protected output handle. </div>
<div> </div>



## -remarks



The DirectX graphics kernel subsystem calls <i>DxgkDdiOPMDestroyProtectedOutput</i> when it finishes using the protected output object.

<i>DxgkDdiOPMDestroyProtectedOutput</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a>
 

 

