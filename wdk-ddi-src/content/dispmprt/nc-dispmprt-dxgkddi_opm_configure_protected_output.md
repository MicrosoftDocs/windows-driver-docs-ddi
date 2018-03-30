---
UID: NC:dispmprt.DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
title: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
author: windows-driver-content
description: The DxgkDdiOPMConfigureProtectedOutput function configures the given protected output object.
old-location: display\dxgkddiopmconfigureprotectedoutput.htm
old-project: display
ms.assetid: a7829587-c1e7-43ec-a0bb-92bca94b7c3d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT, Dm_Opm_functions_4e8394b3-68b4-4747-a375-a767edbccc2c.xml, DxgkDdiOPMConfigureProtectedOutput, DxgkDdiOPMConfigureProtectedOutput callback function [Display Devices], display.dxgkddiopmconfigureprotectedoutput, dispmprt/DxgkDdiOPMConfigureProtectedOutput
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
-	DxgkDdiOPMConfigureProtectedOutput
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback


## -description


The<i> DxgkDdiOPMConfigureProtectedOutput</i> function configures the given protected output object.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


### -param PDXGKMDT_OPM_CONFIGURE_PARAMETERS


### -param AdditionalParametersSize [in]

The size, in bytes, of the additional parameters in the buffer that is pointed to by <i>AdditionalParameters</i>. For Certified Output Protection Protocol (COPP) emulation, this is 0. 


### -param PVOID








#### - AdditionalParameters [in]

A pointer to a buffer that holds the additional parameters that are used to configure the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. For COPP emulation, this is <b>NULL</b>. If the <i>AdditionalParametersSize</i> parameter is set to 0, <i>AdditionalParameters</i> is always set to <b>NULL</b>. 


#### - Parameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560849">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a> structure that contains parameters that are used to configure the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. 


## -returns



<i>DxgkDdiOPMConfigureProtectedOutput</i> returns one of the following values:

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
The function successfully configured the protected output object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiOPMConfigureProtectedOutput</i> cannot allocate memory required for it to complete. 

</td>
</tr>
</table>
 

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



The DirectX graphics kernel subsystem calls <a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a> or <a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a> to retrieve information about the output and then calls <i>DxgkDdiOPMConfigureProtectedOutput</i> one or more times to configure the output.

<i>DxgkDdiOPMConfigureProtectedOutput</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560849">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>
 

 

