---
UID: NC:dispmprt.DXGKDDI_OPM_GET_RANDOM_NUMBER
title: DXGKDDI_OPM_GET_RANDOM_NUMBER
author: windows-driver-content
description: The DxgkDdiOPMGetRandomNumber function retrieves the given protected output object's 128-bit cryptographically secure random number.
old-location: display\dxgkddiopmgetrandomnumber.htm
old-project: display
ms.assetid: 91b07a5c-ed25-4268-bd6d-273ae8b1ac28
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_OPM_GET_RANDOM_NUMBER, Dm_Opm_functions_a7d335ef-61bf-452a-a811-20048ff28dbf.xml, DxgkDdiOPMGetRandomNumber, DxgkDdiOPMGetRandomNumber callback function [Display Devices], display.dxgkddiopmgetrandomnumber, dispmprt/DxgkDdiOPMGetRandomNumber
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
-	DxgkDdiOPMGetRandomNumber
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_OPM_GET_RANDOM_NUMBER callback


## -description


The<i> DxgkDdiOPMGetRandomNumber</i> function retrieves the given protected output object's 128-bit cryptographically secure random number.


## -prototype


````
DXGKDDI_OPM_GET_RANDOM_NUMBER DxgkDdiOPMGetRandomNumber;

NTSTATUS DxgkDdiOPMGetRandomNumber(
  _In_  PVOID                      MiniportDeviceContext,
  _In_  HANDLE                     ProtectedOutputHandle,
  _Out_ PDXGKMDT_OPM_RANDOM_NUMBER RandomNumber
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


### -param RandomNumber [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_random_number.md">DXGKMDT_OPM_RANDOM_NUMBER</a> structure that receives the protected output object's 128-bit cryptographically secure random number if <i>DxgkDdiOPMGetRandomNumber</i> returns successfully.

If <i>DxgkDdiOPMGetRandomNumber</i> fails, the value that <i>RandomNumber</i> points to is unchanged.

Each protected output object must have a different 128-bit cryptographically secure random number associated with it. 


## -returns



<i>DxgkDdiOPMGetRandomNumber</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. 




## -remarks



<i>DxgkDdiOPMGetRandomNumber</i> is called only once for each protected output and is never called after the call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function occurs.

For more information about cryptographically secure random numbers, see section 2.8 in <i>Applied Cryptography</i>, Second Edition.

<i>DxgkDdiOPMGetRandomNumber</i> should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_random_number.md">DXGKMDT_OPM_RANDOM_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_GET_RANDOM_NUMBER callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

