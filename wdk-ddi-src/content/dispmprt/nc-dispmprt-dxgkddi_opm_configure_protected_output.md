---
UID: NC:dispmprt.DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
title: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT (dispmprt.h)
description: The DxgkDdiOPMConfigureProtectedOutput function configures the given protected output object.
old-location: display\dxgkddiopmconfigureprotectedoutput.htm
tech.root: display
ms.assetid: a7829587-c1e7-43ec-a0bb-92bca94b7c3d
ms.date: 05/10/2018
keywords: ["DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback function"]
ms.keywords: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT, DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback, Dm_Opm_functions_4e8394b3-68b4-4747-a375-a767edbccc2c.xml, DxgkDdiOPMConfigureProtectedOutput, DxgkDdiOPMConfigureProtectedOutput callback function [Display Devices], display.dxgkddiopmconfigureprotectedoutput, dispmprt/DxgkDdiOPMConfigureProtectedOutput
f1_keywords:
 - "dispmprt/DxgkDdiOPMConfigureProtectedOutput"
 - "DxgkDdiOPMConfigureProtectedOutput"
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
- DxgkDdiOPMConfigureProtectedOutput
targetos: Windows
req.typenames: 
---

# DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback function


## -description


The<i> DxgkDdiOPMConfigureProtectedOutput</i> function configures the given protected output object.


## -prototype


```cpp
DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT DxgkDdiOPMConfigureProtectedOutput;

NTSTATUS DxgkDdiOPMConfigureProtectedOutput(
  _In_       PVOID                             MiniportDeviceContext,
  _In_       HANDLE                            ProtectedOutputHandle,
  _In_ const PDXGKMDT_OPM_CONFIGURE_PARAMETERS Parameters,
  _In_       ULONG                             AdditionalParametersSize,
  _In_ const PVOID                             AdditionalParameters
)
{ ... }
```


## -parameters




### -param MiniportDeviceContext 

[in] A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle 

[in] The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


### -param PDXGKMDT_OPM_CONFIGURE_PARAMETERS

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a> structure that contains parameters that are used to configure the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter.

### -param AdditionalParametersSize 

[in] The size, in bytes, of the additional parameters in the buffer that is pointed to by <i>AdditionalParameters</i>. For Certified Output Protection Protocol (COPP) emulation, this is 0.


### -param VOID

*AdditionalParameters* [in]

A pointer to a buffer that holds the additional parameters that are used to configure the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. For COPP emulation, this is <b>NULL</b>. If the <i>AdditionalParametersSize</i> parameter is set to 0, <i>AdditionalParameters</i> is always set to <b>NULL</b>.






## -returns



<i>DxgkDdiOPMConfigureProtectedOutput</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully configured the protected output object.|
|STATUS_NO_MEMORY|DxgkDdiOPMConfigureProtectedOutput cannot allocate memory required for it to complete.|
 

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



The DirectX graphics kernel subsystem calls <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> to retrieve information about the output and then calls <i>DxgkDdiOPMConfigureProtectedOutput</i> one or more times to configure the output.

<i>DxgkDdiOPMConfigureProtectedOutput</i> should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>



 

 


