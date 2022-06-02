---
UID: NC:dispmprt.DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
title: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT (dispmprt.h)
description: The DxgkDdiOPMConfigureProtectedOutput function configures the given protected output object.
old-location: display\dxgkddiopmconfigureprotectedoutput.htm
tech.root: display
ms.date: 05/31/2022
keywords: ["DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback function"]
ms.keywords: DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT, DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback, Dm_Opm_functions_4e8394b3-68b4-4747-a375-a767edbccc2c.xml, DxgkDdiOPMConfigureProtectedOutput, DxgkDdiOPMConfigureProtectedOutput callback function [Display Devices], display.dxgkddiopmconfigureprotectedoutput, dispmprt/DxgkDdiOPMConfigureProtectedOutput
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
 - dispmprt/DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT
---

# DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback function

## -description

The **DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT** function configures the given protected output object.

## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to the DirectX graphics kernel subsystem.

### -param ProtectedOutputHandle [in]

The handle to a protected output object. The [**DxgkDdiOPMCreateProtectedOutput**](nc-dispmprt-dxgkddi_opm_create_protected_output.md) function creates the protected output object and returns the handle to the object.

### -param Parameters [in]

A pointer to a [**DXGKMDT_OPM_CONFIGURE_PARAMETERS**](..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md) structure that contains parameters that are used to configure the protected output object whose handle is specified in the **ProtectedOutputHandle** parameter.

### -param AdditionalParametersSize [in]

The size, in bytes, of the additional parameters in the buffer that is pointed to by **AdditionalParameters**. For Certified Output Protection Protocol (COPP) emulation, this is 0.

### -param AdditionalParameters [in]

A pointer to a buffer that holds the additional parameters that are used to configure the protected output object whose handle is specified in the **ProtectedOutputHandle** parameter. For COPP emulation, this is NULL. If the **AdditionalParametersSize** parameter is set to 0, **AdditionalParameters** is always set to NULL.

## -returns

**DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT** returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully configured the protected output object.|
|STATUS_NO_MEMORY|DxgkDdiOPMConfigureProtectedOutput cannot allocate memory required for it to complete.|

This function might also return other error codes that are defined in *Ntstatus.h*.

## -remarks

The DirectX graphics kernel subsystem calls [**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md) or [**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) to retrieve information about the output and then calls **DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT** one or more times to configure the output.

**DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT** should be made pageable.

## -see-also

[**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md)

[**DxgkDdiOPMCreateProtectedOutput**](nc-dispmprt-dxgkddi_opm_create_protected_output.md)

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)

[**DXGKMDT_OPM_CONFIGURE_PARAMETERS**](..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md)

[**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md)
