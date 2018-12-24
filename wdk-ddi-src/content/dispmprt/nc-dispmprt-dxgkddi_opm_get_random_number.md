---
UID: NC:dispmprt.DXGKDDI_OPM_GET_RANDOM_NUMBER
title: DXGKDDI_OPM_GET_RANDOM_NUMBER
description: The DxgkDdiOPMGetRandomNumber function retrieves the given protected output object's 128-bit cryptographically secure random number.
old-location: display\dxgkddiopmgetrandomnumber.htm
tech.root: display
ms.assetid: 91b07a5c-ed25-4268-bd6d-273ae8b1ac28
ms.date: 05/10/2018
ms.keywords: DXGKDDI_OPM_GET_RANDOM_NUMBER, DXGKDDI_OPM_GET_RANDOM_NUMBER callback, Dm_Opm_functions_a7d335ef-61bf-452a-a811-20048ff28dbf.xml, DxgkDdiOPMGetRandomNumber, DxgkDdiOPMGetRandomNumber callback function [Display Devices], display.dxgkddiopmgetrandomnumber, dispmprt/DxgkDdiOPMGetRandomNumber
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
-	DxgkDdiOPMGetRandomNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_OPM_GET_RANDOM_NUMBER callback function


## -description


The<i> DxgkDdiOPMGetRandomNumber</i> function retrieves the given protected output object's 128-bit cryptographically secure random number.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


### -param RandomNumber [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560906">DXGKMDT_OPM_RANDOM_NUMBER</a> structure that receives the protected output object's 128-bit cryptographically secure random number if <i>DxgkDdiOPMGetRandomNumber</i> returns successfully.

If <i>DxgkDdiOPMGetRandomNumber</i> fails, the value that <i>RandomNumber</i> points to is unchanged.

Each protected output object must have a different 128-bit cryptographically secure random number associated with it. 


## -returns



<i>DxgkDdiOPMGetRandomNumber</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. 




## -remarks



<i>DxgkDdiOPMGetRandomNumber</i> is called only once for each protected output and is never called after the call to the <a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function occurs.

For more information about cryptographically secure random numbers, see section 2.8 in <i>Applied Cryptography</i>, Second Edition.

<i>DxgkDdiOPMGetRandomNumber</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560906">DXGKMDT_OPM_RANDOM_NUMBER</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a>



<a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
 

 

