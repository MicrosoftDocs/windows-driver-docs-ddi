---
UID: NC:dispmprt.DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
title: DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
author: windows-driver-content
description: The DxgkDdiOPMGetCOPPCompatibleInformation function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object.
old-location: display\dxgkddiopmgetcoppcompatibleinformation.htm
old-project: display
ms.assetid: 9f15df1e-bdf5-4634-97f1-78515664b594
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION, Dm_Opm_functions_7873b0b1-3983-49c4-8192-b0c59d5ae01c.xml, DxgkDdiOPMGetCOPPCompatibleInformation, DxgkDdiOPMGetCOPPCompatibleInformation callback function [Display Devices], display.dxgkddiopmgetcoppcompatibleinformation, dispmprt/DxgkDdiOPMGetCOPPCompatibleInformation
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiOPMGetCOPPCompatibleInformation
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback


## -description


The<i> DxgkDdiOPMGetCOPPCompatibleInformation</i> function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object.


## -prototype


````
DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION DxgkDdiOPMGetCOPPCompatibleInformation;

NTSTATUS DxgkDdiOPMGetCOPPCompatibleInformation(
  _In_        PVOID                                            MiniportDeviceContext,
  _In_        HANDLE                                           ProtectedOutputHandle,
  _In_  const PDXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS Parameters,
  _Out_       PDXGKMDT_OPM_REQUESTED_INFORMATION               RequestedInformation
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.


### -param ProtectedOutputHandle [in]

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object. The protected output object that corresponds to this handle should have COPP semantics.


### -param PDXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS


### -param RequestedInformation [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that receives the protected output object's COPP-compatible information if <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> returns successfully.

If <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> fails, the value that <i>RequestedInformation</i> points to is unchanged.


#### - Parameters [in]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a> structure that contains the type of COPP-compatible information to retrieve from the protected output object whose handle is specified in the <i>ProtectedOutputHandle</i> parameter. <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> determines if the parameters contain a valid request from the application that indirectly created the protected output object. For more information, see the Remarks section. 


## -returns



<i>DxgkDdiOPMGetCOPPCompatibleInformation</i> returns one of the following values.

This function might also return other error codes that are defined in Ntstatus.h.




## -remarks



The DirectX graphics kernel subsystem should call <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> only if the output has COPP semantics.

Before the DirectX graphics kernel subsystem passes the protected output handle to the <i>ProtectedOutputHandle</i> parameter in a call to <i>DxgkDdiOPMGetCOPPCompatibleInformation</i>, the DirectX graphics kernel subsystem always passes the protected output handle to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> functions. 

Following are some facts that pertain to <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> and that do not pertain to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function:

<ul>
<li>
The DirectX graphics kernel subsystem can pass a handle to a protected output only with COPP semantics. 

</li>
<li>
The <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter points to is not signed.

</li>
<li>
The DirectX graphics kernel subsystem can pass the DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING and DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUIDs in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

</li>
<li>
The DirectX graphics kernel subsystem cannot pass the DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION GUID in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

</li>
<li>
The DirectX graphics kernel subsystem can specify DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP in the first 4 bytes of the <b>abParameters</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS along with the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

</li>
<li>
The DirectX graphics kernel subsystem cannot specify DXGKMDT_OPM_PROTECTION_TYPE_HDCP in the first 4 bytes of the <b>abParameters</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS along with the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS. 

</li>
</ul>
The driver must perform the following sequence when its <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> function is called.

<ol>
<li>
Verify that the protected output handle that was passed to the <i>ProtectedOutputHandle</i> parameter of <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> has COPP semantics.

</li>
<li>
Retrieve the requested information.

</li>
<li>
Copy the random number that the <b>rnRandomNumber</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS specifies to the <b>rnRandomNumber</b> member of the DXGKMDT_OPM_STANDARD_INFORMATION, DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT, DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING, or DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION structure. The structure that is used depends on the type of information that the caller requested. The structure is set in the <b>abRequestedInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that the <i>RequestedInformation</i> parameter points to.

</li>
<li>
Sign the DXGKMDT_OPM_REQUESTED_INFORMATION structure and place the signature in the <b>omac</b> member of DXGKMDT_OPM_REQUESTED_INFORMATION. The AES block cipher and the OMAC-1 signing algorithm should be used to sign the structure. For information about AES, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. For information about OMAC-1, see the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a> reference page. 

</li>
</ol>
Initially, the DirectX graphics kernel subsystem calls <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> to retrieve information about the output and then calls <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> one or more times to configure the output. Subsequently, the DirectX graphics kernel subsystem calls <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> without also calling <i>DxgkDdiOPMConfigureProtectedOutput</i>.

<i>DxgkDdiOPMGetCOPPCompatibleInformation</i> should be made pageable.




## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

