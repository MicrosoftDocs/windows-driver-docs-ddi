---
UID: NC:dispmprt.DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
title: DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION (dispmprt.h)
description: The DxgkDdiOPMGetCOPPCompatibleInformation function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object.
old-location: display\dxgkddiopmgetcoppcompatibleinformation.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback function"]
ms.keywords: DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION, DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback, Dm_Opm_functions_7873b0b1-3983-49c4-8192-b0c59d5ae01c.xml, DxgkDdiOPMGetCOPPCompatibleInformation, DxgkDdiOPMGetCOPPCompatibleInformation callback function [Display Devices], display.dxgkddiopmgetcoppcompatibleinformation, dispmprt/DxgkDdiOPMGetCOPPCompatibleInformation
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
 - DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
 - dispmprt/DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
---

# DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback function

## -description

The *DxgkDdiOPMGetCOPPCompatibleInformation* function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object.

## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's [*DxgkDdiAddDevice*](nc-dispmprt-dxgkddi_add_device.md) function provided this handle to the DirectX graphics kernel subsystem.

### -param ProtectedOutputHandle [in]

The handle to a protected output object. The [*DxgkDdiOPMCreateProtectedOutput*](nc-dispmprt-dxgkddi_opm_create_protected_output.md) function creates the protected output object and returns the handle to the object. The protected output object that corresponds to this handle should have COPP semantics.

### -param PDXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS

A pointer to a [**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md) structure that contains the type of COPP-compatible information to retrieve from the protected output object whose handle is specified in the **ProtectedOutputHandle** parameter. *DxgkDdiOPMGetCOPPCompatibleInformation* determines if the parameters contain a valid request from the application that indirectly created the protected output object. For more information, see the Remarks section.

### -param RequestedInformation [out]

A pointer to a [**DXGKMDT_OPM_REQUESTED_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_requested_information.md) structure that receives the protected output object's COPP-compatible information if *DxgkDdiOPMGetCOPPCompatibleInformation* returns successfully.

If *DxgkDdiOPMGetCOPPCompatibleInformation* fails, the value that **RequestedInformation** points to is unchanged.

## -returns

*DxgkDdiOPMGetCOPPCompatibleInformation* returns STATUS_SUCCESS or an *Ntstatus.h* error code.

## -prototype

```cpp
DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION DxgkDdiOPMGetCOPPCompatibleInformation;

NTSTATUS DxgkDdiOPMGetCOPPCompatibleInformation(
  _In_        PVOID                                            MiniportDeviceContext,
  _In_        HANDLE                                           ProtectedOutputHandle,
  _In_  const PDXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS Parameters,
  _Out_       PDXGKMDT_OPM_REQUESTED_INFORMATION               RequestedInformation
)
{ ... }
```

## -remarks

The DirectX graphics kernel subsystem should call *DxgkDdiOPMGetCOPPCompatibleInformation* only if the output has COPP semantics.

Before the DirectX graphics kernel subsystem passes the protected output handle to the **ProtectedOutputHandle** parameter in a call to *DxgkDdiOPMGetCOPPCompatibleInformation*, the DirectX graphics kernel subsystem always passes the protected output handle to the [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) and [*DxgkDdiOPMGetRandomNumber*](nc-dispmprt-dxgkddi_opm_get_random_number.md) functions.

Following are some facts that pertain to *DxgkDdiOPMGetCOPPCompatibleInformation* and that do not pertain to the [*DxgkDdiOPMGetInformation*](nc-dispmprt-dxgkddi_opm_get_information.md) function:

* The DirectX graphics kernel subsystem can pass a handle to a protected output only with COPP semantics.

* The [**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md) structure that the **Parameters** parameter points to is not signed.

* The DirectX graphics kernel subsystem can pass the DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING and DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUIDs in the **guidInformation** member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

* The DirectX graphics kernel subsystem cannot pass the DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION GUID in the **guidInformation** member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

* The DirectX graphics kernel subsystem can specify DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP in the first 4 bytes of the **abParameters** member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS along with the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID in the **guidInformation** member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

* The DirectX graphics kernel subsystem cannot specify DXGKMDT_OPM_PROTECTION_TYPE_HDCP in the first 4 bytes of the **abParameters** member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS along with the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID in the **guidInformation** member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

The driver must perform the following sequence when its *DxgkDdiOPMGetCOPPCompatibleInformation* function is called.

1. Verify that the protected output handle that was passed to the **ProtectedOutputHandle** parameter of *DxgkDdiOPMGetCOPPCompatibleInformation* has COPP semantics.

2. Retrieve the requested information.

3. Copy the random number that the **rnRandomNumber** member of [**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md) specifies to the **rnRandomNumber** member of the DXGKMDT_OPM_STANDARD_INFORMATION, DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT, DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING, or DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION structure. The structure that is used depends on the type of information that the caller requested. The structure is set in the **abRequestedInformation** member of the [**DXGKMDT_OPM_REQUESTED_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_requested_information.md) structure that the **RequestedInformation** parameter points to.

4. Sign the [**DXGKMDT_OPM_REQUESTED_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_requested_information.md) structure and place the signature in the **omac** member of DXGKMDT_OPM_REQUESTED_INFORMATION. The AES block cipher and the OMAC-1 signing algorithm should be used to sign the structure. For information about AES, see the [RSA Laboratories](https://www.rsa.com) website. For information about OMAC-1, see the [**DXGKMDT_OPM_OMAC**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_omac.md) reference page.

Initially, the DirectX graphics kernel subsystem calls *DxgkDdiOPMGetCOPPCompatibleInformation* to retrieve information about the output and then calls [*DxgkDdiOPMConfigureProtectedOutput*](nc-dispmprt-dxgkddi_opm_configure_protected_output.md) one or more times to configure the output. Subsequently, the DirectX graphics kernel subsystem calls *DxgkDdiOPMGetCOPPCompatibleInformation* without also calling *DxgkDdiOPMConfigureProtectedOutput*.

*DxgkDdiOPMGetCOPPCompatibleInformation* should be made pageable.

## -see-also

[*DxgkDdiAddDevice*](nc-dispmprt-dxgkddi_add_device.md)

[*DxgkDdiOPMConfigureProtectedOutput*](nc-dispmprt-dxgkddi_opm_configure_protected_output.md)

[*DxgkDdiOPMCreateProtectedOutput*](nc-dispmprt-dxgkddi_opm_create_protected_output.md)

[*DxgkDdiOPMGetInformation*](nc-dispmprt-dxgkddi_opm_get_information.md)

[*DxgkDdiOPMGetRandomNumber*](nc-dispmprt-dxgkddi_opm_get_random_number.md)

[*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md)

[**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md)

[**DXGKMDT_OPM_OMAC**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_omac.md)

[**DXGKMDT_OPM_REQUESTED_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_requested_information.md)
