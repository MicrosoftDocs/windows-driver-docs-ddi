---
UID: NC:dispmprt.DXGKDDI_OPM_GET_INFORMATION
title: DXGKDDI_OPM_GET_INFORMATION
author: windows-driver-content
description: The DxgkDdiOPMGetInformation function retrieves information from the given protected output object.
old-location: display\dxgkddiopmgetinformation.htm
old-project: display
ms.assetid: 3d6559e5-776e-4fc0-b99a-8818cbcc289d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
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
req.alt-api: DxgkDdiOPMGetInformation
req.alt-loc: dispmprt.h
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
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGKDDI_OPM_GET_INFORMATION callback



## -description
The<i> DxgkDdiOPMGetInformation</i> function retrieves information from the given protected output object.



## -prototype

````
DXGKDDI_OPM_GET_INFORMATION DxgkDdiOPMGetInformation;

NTSTATUS DxgkDdiOPMGetInformation(
  _In_        PVOID                              MiniportDeviceContext,
  _In_        HANDLE                             ProtectedOutputHandle,
  _In_  const PDXGKMDT_OPM_GET_INFO_PARAMETERS   Parameters,
  _Out_       PDXGKMDT_OPM_REQUESTED_INFORMATION RequestedInformation
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object. The protected output object that corresponds to this handle should have OPM semantics.


### -param Parameters [in]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure that contains parameters that are used to retrieve information from a protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. <i>DxgkDdiOPMGetInformation</i> determines if the parameters contain a valid request from the application that indirectly created the protected output object. For more information, see the Remarks section. 


### -param RequestedInformation [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that receives the protected output object's information if <i>DxgkDdiOPMGetInformation</i> returns successfully.

If <i>DxgkDdiOPMGetInformation</i> fails, the value that <i>RequestedInformation</i> points to is unchanged.


## -returns
<i>DxgkDdiOPMGetInformation</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
<dd>
The function successfully retrieved the protected output object's information.

</dd>
<dt><b>STATUS_GRAPHICS_OPM_PROTECTED_OUTPUT_DOES_NOT_HAVE_OPM_SEMANTICS</b></dt>
<dd>
The protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter does not have OPM semantics. The DirectX graphics kernel subsystem should call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function instead of <i>DxgkDdiOPMGetInformation </i>for protected output objects with COPP semantics.

</dd>
<dt><b>STATUS_GRAPHICS_OPM_PROTECTED_OUTPUT_DOES_NOT_HAVE_COPP_SEMANTICS</b></dt>
<dd>
COPP-specific information was requested. <i>DxgkDdiOPMGetInformation</i> cannot return COPP-specific information because it can return only OPM-specific information. Callers that require COPP-specific information should create a protected output with COPP semantics and then call <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>. Following are the types of requests (that are specified in the <b>guidInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter points to) that cause <i>DxgkDdiOPMGetInformation</i> to return this value:



<dl>
<dt><a id="DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION"></a><a id="dxgkmdt_opm_get_connected_hdcp_device_information"></a>DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION</dt>
<dd>
This request is used by COPP applications when they enable High-bandwidth Digital Content Protection (HDCP). For more information about HDCP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>.

</dd>
<dt><a id="DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL_or_DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL_and_the_first_4_bytes_of_the_abParameters_member_of_DXGKMDT_OPM_GET_INFO_PARAMETERS_contain_DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP"></a><a id="dxgkmdt_opm_get_virtual_protection_level_or_dxgkmdt_opm_get_actual_protection_level_and_the_first_4_bytes_of_the_abparameters_member_of_dxgkmdt_opm_get_info_parameters_contain_dxgkmdt_opm_protection_type_copp_compatible_hdcp"></a><a id="DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL_OR_DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL_AND_THE_FIRST_4_BYTES_OF_THE_ABPARAMETERS_MEMBER_OF_DXGKMDT_OPM_GET_INFO_PARAMETERS_CONTAIN_DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP"></a>DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL and the first 4 bytes of the <b>abParameters</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> contain DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP</dt>
<dd>
DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP is used to determine an output's virtual or actual COPP-compatible HDCP protection level. OPM applications should use DXGKMDT_OPM_PROTECTION_TYPE_HDCP instead of DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP.

</dd>
<dt><a id="DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING"></a><a id="dxgkmdt_opm_get_acp_and_cgmsa_signaling"></a>DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING</dt>
<dd>
OPM does not support this information request. 

</dd>
</dl>
</dd>
<dt><b>STATUS_GRAPHICS_OPM_OUTPUT_DOES_NOT_SUPPORT_HDCP</b></dt>
<dd>
The graphics adapter does not support HDCP. 

Following are the types of requests (that are specified in the <b>guidInformation</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>) that cause <i>DxgkDdiOPMGetInformation</i> to return this value:



<dl>
<dt><a id="DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION"></a><a id="dxgkmdt_opm_get_current_hdcp_srm_version"></a>DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION</dt>
<dd></dd>
<dt><a id="DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL_or_DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL_and_the_first_4_bytes_of_the_abParameters_member_of_DXGKMDT_OPM_GET_INFO_PARAMETERS_contain_DXGKMDT_OPM_PROTECTION_TYPE_HDCP._"></a><a id="dxgkmdt_opm_get_virtual_protection_level_or_dxgkmdt_opm_get_actual_protection_level_and_the_first_4_bytes_of_the_abparameters_member_of_dxgkmdt_opm_get_info_parameters_contain_dxgkmdt_opm_protection_type_hdcp._"></a><a id="DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL_OR_DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL_AND_THE_FIRST_4_BYTES_OF_THE_ABPARAMETERS_MEMBER_OF_DXGKMDT_OPM_GET_INFO_PARAMETERS_CONTAIN_DXGKMDT_OPM_PROTECTION_TYPE_HDCP._"></a>DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL and the first 4 bytes of the <b>abParameters</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> contain DXGKMDT_OPM_PROTECTION_TYPE_HDCP. </dt>
<dd></dd>
</dl>
</dd>
<dt><b>STATUS_GRAPHICS_OPM_MONITOR_DOES_NOT_SUPPORT_HDCP</b></dt>
<dd>
The graphics adapter supports HDCP, but the monitor that is connected to the protected output's physical video output does not support HDCP. 

Following are the types of requests (that are specified in the <b>guidInformation</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>) that cause <i>DxgkDdiOPMGetInformation</i> to return this value:



<dl>
<dt><a id="DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION"></a><a id="dxgkmdt_opm_get_current_hdcp_srm_version"></a>DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION</dt>
<dd>
Requests the version number of the current High-bandwidth Digital Content Protection (HDCP) System Renewability Message (SRM) for the protected output.

</dd>
<dt><a id="DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL_or_DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL_and_the_first_4_bytes_of_the_abParameters_member_of_DXGKMDT_OPM_GET_INFO_PARAMETERS_contain_DXGKMDT_OPM_PROTECTION_TYPE_HDCP."></a><a id="dxgkmdt_opm_get_virtual_protection_level_or_dxgkmdt_opm_get_actual_protection_level_and_the_first_4_bytes_of_the_abparameters_member_of_dxgkmdt_opm_get_info_parameters_contain_dxgkmdt_opm_protection_type_hdcp."></a><a id="DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL_OR_DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL_AND_THE_FIRST_4_BYTES_OF_THE_ABPARAMETERS_MEMBER_OF_DXGKMDT_OPM_GET_INFO_PARAMETERS_CONTAIN_DXGKMDT_OPM_PROTECTION_TYPE_HDCP."></a>DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL and the first 4 bytes of the <b>abParameters</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> contain DXGKMDT_OPM_PROTECTION_TYPE_HDCP.</dt>
<dd>
Requests the virtual or actual HDCP protection level.

</dd>
</dl>
</dd>
<dt><b>STATUS_GRAPHICS_OPM_OUTPUT_DOES_NOT_SUPPORT_ACP</b></dt>
<dd>
The protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter does not support Analog Copy Protection (ACP), the <b>guidInformation</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> specifies DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL, and the first 4 bytes of the <b>abParameters</b> member of <b>DXGKMDT_OPM_GET_INFO_PARAMETERS</b> contain DXGKMDT_OPM_PROTECTION_TYPE_ACP. ACP protects analog TV signals. For more information about ACP, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71273">Rovi (formerly Macrovision)</a> website.

</dd>
<dt><b>STATUS_GRAPHICS_OPM_OUTPUT_DOES_NOT_SUPPORT_CGMSA</b></dt>
<dd>
The protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter does not support Content Generation Management System Analog (CGMS-A) and redistributable control, the <b>guidInformation</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> specifies DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL, and the first 4 bytes of the <b>abParameters</b> member of <b>DXGKMDT_OPM_GET_INFO_PARAMETERS</b> contain DXGKMDT_OPM_PROTECTION_TYPE_CGMSA. CGMS-A protects analog TV signals. For more information about CGMS-A, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70568">CGMS-A article</a>. 

</dd>
<dt><b>STATUS_GRAPHICS_OPM_HDCP_SRM_NEVER_SET</b></dt>
<dd>
The graphics adapter supports HDCP, the <b>guidInformation</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> specifies DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION, and the protected output's user never provided a System Renewability Message (SRM) to the protected output. For more information about the SRM, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>. 

</dd>
<dt><b>STATUS_GRAPHICS_OPM_INVALID_INFORMATION_REQUEST</b></dt>
<dd>
The <b>ulSequenceNumber</b> or <b>omac</b> member of <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> contain an invalid sequence number or signature respectively. 

</dd>
</dl>The function successfully retrieved the protected output object's information.

The protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter does not have OPM semantics. The DirectX graphics kernel subsystem should call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function instead of <i>DxgkDdiOPMGetInformation </i>for protected output objects with COPP semantics.

COPP-specific information was requested. <i>DxgkDdiOPMGetInformation</i> cannot return COPP-specific information because it can return only OPM-specific information. Callers that require COPP-specific information should create a protected output with COPP semantics and then call <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>. Following are the types of requests (that are specified in the <b>guidInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter points to) that cause <i>DxgkDdiOPMGetInformation</i> to return this value:


## -remarks
The DirectX graphics kernel subsystem should call <i>DxgkDdiOPMGetInformation</i> only if the output has OPM semantics.

Before the DirectX graphics kernel subsystem passes the protected output handle to the <i>ProtectedOutputHandle</i> parameter in a call to <i>DxgkDdiOPMGetInformation</i>, the DirectX graphics kernel subsystem always passes the protected output handle to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> functions. 

<i>DxgkDdiOPMGetInformation</i> retrieves one of the following types of information:  

The protected output's connector type.

The content protection types that the protected output supports. Protected outputs can currently support ACP, CGMS-A, and HDCP. 

The protected output's current virtual protection level for a particular protection type. 

The physical output's actual protection level for a particular protection type. 

The version of the HDCP SRM that the protected output currently uses. 

The type of expansion bus that the graphics adapter uses and how the graphics adapter is connected to the computer's north bridge. 

The format of the images that the graphics adapter sends from the physical output to the monitor. 

The <b>guidInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter points to should never contain the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION and DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING GUIDs because only COPP applications should specify these GUIDs. 


## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_GET_INFORMATION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

