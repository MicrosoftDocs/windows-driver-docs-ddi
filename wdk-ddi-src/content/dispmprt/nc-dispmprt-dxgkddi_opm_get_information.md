---
UID: NC:dispmprt.DXGKDDI_OPM_GET_INFORMATION
title: DXGKDDI_OPM_GET_INFORMATION (dispmprt.h)
description: The DxgkDdiOPMGetInformation function retrieves information from the given protected output object.
old-location: display\dxgkddiopmgetinformation.htm
tech.root: display
ms.assetid: 3d6559e5-776e-4fc0-b99a-8818cbcc289d
ms.date: 05/10/2018
ms.keywords: DXGKDDI_OPM_GET_INFORMATION, DXGKDDI_OPM_GET_INFORMATION callback, Dm_Opm_functions_6d4af4a5-4390-49f1-a557-735bf2c90ce6.xml, DxgkDdiOPMGetInformation, DxgkDdiOPMGetInformation callback function [Display Devices], display.dxgkddiopmgetinformation, dispmprt/DxgkDdiOPMGetInformation
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
-	DxgkDdiOPMGetInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_OPM_GET_INFORMATION callback function


## -description


The<i> DxgkDdiOPMGetInformation</i> function retrieves information from the given protected output object.


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


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object. The protected output object that corresponds to this handle should have OPM semantics.


### -param PDXGKMDT_OPM_GET_INFO_PARAMETERS

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure that contains parameters that are used to retrieve information from a protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. <i>DxgkDdiOPMGetInformation</i> determines if the parameters contain a valid request from the application that indirectly created the protected output object. For more information, see the Remarks section.

### -param RequestedInformation [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that receives the protected output object's information if <i>DxgkDdiOPMGetInformation</i> returns successfully.

If <i>DxgkDdiOPMGetInformation</i> fails, the value that <i>RequestedInformation</i> points to is unchanged.






## -returns



<i>DxgkDdiOPMGetInformation</i> returns one of the following values:

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



The DirectX graphics kernel subsystem should call <i>DxgkDdiOPMGetInformation</i> only if the output has OPM semantics.

Before the DirectX graphics kernel subsystem passes the protected output handle to the <i>ProtectedOutputHandle</i> parameter in a call to <i>DxgkDdiOPMGetInformation</i>, the DirectX graphics kernel subsystem always passes the protected output handle to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> functions.

<i>DxgkDdiOPMGetInformation</i> retrieves one of the following types of information:

<ul>
<li>
The protected output's connector type.

</li>
<li>
The content protection types that the protected output supports. Protected outputs can currently support ACP, CGMS-A, and HDCP.

</li>
<li>
The protected output's current virtual protection level for a particular protection type.

</li>
<li>
The physical output's actual protection level for a particular protection type.

</li>
<li>
The version of the HDCP SRM that the protected output currently uses.

</li>
<li>
The type of expansion bus that the graphics adapter uses and how the graphics adapter is connected to the computer's north bridge.

</li>
<li>
The format of the images that the graphics adapter sends from the physical output to the monitor.

</li>
</ul>
The <b>guidInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter points to should never contain the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION and DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING GUIDs because only COPP applications should specify these GUIDs.

The first 4 bytes of the <b>abParameters</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> should never contain the DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP protection type when the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID is specified in the <b>guidInformation</b> member of <b>DXGKMDT_OPM_GET_INFO_PARAMETERS</b> because only COPP applications use this protection type.

The driver must perform the following sequence when its <i>DxgkDdiOPMGetInformation</i> function is called.

<ol>
<li>
Verify that the protected output handle that was passed to the <i>ProtectedOutputHandle</i> parameter of <i>DxgkDdiOPMGetInformation</i> has OPM semantics.

</li>
<li>
Verify that the information in the <i>Parameters</i> parameter was signed with the protected output object's signing key. The protected output object's signing key was previously set when the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function was called. The Advanced Encryption Standard (AES) block cipher and the OMAC-1 signing algorithm should be used to verify the signature. For information about AES, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. For information about OMAC-1, see the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a> reference page.

</li>
<li>
Retrieve the requested information.

</li>
<li>
Copy the random number that the <b>rnRandomNumber</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> specifies to the <b>rnRandomNumber</b> member in the DXGKMDT_OPM_STANDARD_INFORMATION or DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT structure. The structure that is used depends on the type of information that the caller requested and is set in the <b>abRequestedInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that the <i>RequestedInformation</i> parameter points to.

</li>
<li>
Sign the DXGKMDT_OPM_REQUESTED_INFORMATION structure and place the signature in the <b>omac</b> member of DXGKMDT_OPM_REQUESTED_INFORMATION. The AES block cipher and the OMAC-1 signing algorithm should be used to sign the structure.

</li>
</ol>
Initially, the DirectX graphics kernel subsystem calls <i>DxgkDdiOPMGetInformation</i> to retrieve information about the output and then calls <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> one or more times to configure the output. Subsequently, the DirectX graphics kernel subsystem calls <i>DxgkDdiOPMGetInformation</i> without also calling <i>DxgkDdiOPMConfigureProtectedOutput</i>.

<i>DxgkDdiOPMGetInformation</i> should be made pageable.




## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>



 

 


