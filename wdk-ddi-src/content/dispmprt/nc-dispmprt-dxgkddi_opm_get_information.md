---
UID: NC:dispmprt.DXGKDDI_OPM_GET_INFORMATION
title: DXGKDDI_OPM_GET_INFORMATION (dispmprt.h)
description: The DxgkDdiOPMGetInformation function retrieves information from the given protected output object.
old-location: display\dxgkddiopmgetinformation.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGKDDI_OPM_GET_INFORMATION callback function"]
ms.keywords: DXGKDDI_OPM_GET_INFORMATION, DXGKDDI_OPM_GET_INFORMATION callback, Dm_Opm_functions_6d4af4a5-4390-49f1-a557-735bf2c90ce6.xml, DxgkDdiOPMGetInformation, DxgkDdiOPMGetInformation callback function [Display Devices], display.dxgkddiopmgetinformation, dispmprt/DxgkDdiOPMGetInformation
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
 - DXGKDDI_OPM_GET_INFORMATION
 - dispmprt/DXGKDDI_OPM_GET_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_OPM_GET_INFORMATION
---

# DXGKDDI_OPM_GET_INFORMATION callback function

## -description

The *DxgkDdiOPMGetInformation* function retrieves information from the given protected output object.

## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's [*DxgkDdiAddDevice*](nc-dispmprt-dxgkddi_add_device.md) function provided this handle to the DirectX graphics kernel subsystem.

### -param ProtectedOutputHandle [in]

The handle to a protected output object. The [*DxgkDdiOPMCreateProtectedOutput*](nc-dispmprt-dxgkddi_opm_create_protected_output.md) function creates the protected output object and returns the handle to the object. The protected output object that corresponds to this handle should have OPM semantics.

### -param PDXGKMDT_OPM_GET_INFO_PARAMETERS

A pointer to a [**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md) structure that contains parameters that are used to retrieve information from a protected output object whose handle is specified in the **ProtectedOutputHandle** parameter. *DxgkDdiOPMGetInformation* determines if the parameters contain a valid request from the application that indirectly created the protected output object. For more information, see the Remarks section.

### -param RequestedInformation [out]

A pointer to a [**DXGKMDT_OPM_REQUESTED_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_requested_information.md) structure that receives the protected output object's information if *DxgkDdiOPMGetInformation* returns successfully.

If *DxgkDdiOPMGetInformation* fails, the value that **RequestedInformation** points to is unchanged.

## -returns

*DxgkDdiOPMGetCOPPCompatibleInformation* returns STATUS_SUCCESS or an *Ntstatus.h* error code.

## -prototype

```cpp
DXGKDDI_OPM_GET_INFORMATION DxgkDdiOPMGetInformation;

NTSTATUS DxgkDdiOPMGetInformation(
  _In_        PVOID                              MiniportDeviceContext,
  _In_        HANDLE                             ProtectedOutputHandle,
  _In_  const PDXGKMDT_OPM_GET_INFO_PARAMETERS   Parameters,
  _Out_       PDXGKMDT_OPM_REQUESTED_INFORMATION RequestedInformation
)
{ ... }
```

## -remarks

The DirectX graphics kernel subsystem should call *DxgkDdiOPMGetInformation* only if the output has OPM semantics.

Before the DirectX graphics kernel subsystem passes the protected output handle to the **ProtectedOutputHandle** parameter in a call to *DxgkDdiOPMGetInformation*, the DirectX graphics kernel subsystem always passes the protected output handle to the [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) and [*DxgkDdiOPMGetRandomNumber*](nc-dispmprt-dxgkddi_opm_get_random_number.md) functions.

*DxgkDdiOPMGetInformation* retrieves one of the following types of information:

* The protected output's connector type.
* The content protection types that the protected output supports. Protected outputs can currently support ACP, CGMS-A, and HDCP.
* The protected output's current virtual protection level for a particular protection type.
* The physical output's actual protection level for a particular protection type.
* The version of the HDCP SRM that the protected output currently uses.
* The type of expansion bus that the graphics adapter uses and how the graphics adapter is connected to the computer's north bridge.
* The format of the images that the graphics adapter sends from the physical output to the monitor.

The **guidInformation** member of the [**DXGKMDT_OPM_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md) structure that the **Parameters** parameter points to should never contain the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION and DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING GUIDs because only COPP applications should specify these GUIDs.

The first 4 bytes of the **abParameters** member of [**DXGKMDT_OPM_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md) should never contain the DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP protection type when the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID is specified in the **guidInformation** member of **DXGKMDT_OPM_GET_INFO_PARAMETERS** because only COPP applications use this protection type.

The driver must perform the following sequence when its *DxgkDdiOPMGetInformation* function is called.

1. Verify that the protected output handle that was passed to the **ProtectedOutputHandle** parameter of *DxgkDdiOPMGetInformation* has OPM semantics.

2. Verify that the information in the **Parameters** parameter was signed with the protected output object's signing key. The protected output object's signing key was previously set when the [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) function was called. The Advanced Encryption Standard (AES) block cipher and the OMAC-1 signing algorithm should be used to verify the signature. For information about AES, see the [RSA Laboratories](https://www.rsa.com) website. For information about OMAC-1, see the [**DXGKMDT_OPM_OMAC**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_omac.md) reference page.

3. Retrieve the requested information.

4. Copy the random number that the **rnRandomNumber** member of [**DXGKMDT_OPM_GET_INFO_PARAMETERS**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md) specifies to the **rnRandomNumber** member in the DXGKMDT_OPM_STANDARD_INFORMATION or DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT structure. The structure that is used depends on the type of information that the caller requested and is set in the **abRequestedInformation** member of the [**DXGKMDT_OPM_REQUESTED_INFORMATION**](../d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_requested_information.md) structure that the **RequestedInformation** parameter points to.

5. Sign the DXGKMDT_OPM_REQUESTED_INFORMATION structure and place the signature in the **omac** member of DXGKMDT_OPM_REQUESTED_INFORMATION. The AES block cipher and the OMAC-1 signing algorithm should be used to sign the structure.

Initially, the DirectX graphics kernel subsystem calls *DxgkDdiOPMGetInformation* to retrieve information about the output and then calls [*DxgkDdiOPMConfigureProtectedOutput*](nc-dispmprt-dxgkddi_opm_configure_protected_output.md) one or more times to configure the output. Subsequently, the DirectX graphics kernel subsystem calls *DxgkDdiOPMGetInformation* without also calling *DxgkDdiOPMConfigureProtectedOutput*.

*DxgkDdiOPMGetInformation* should be made pageable.

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
