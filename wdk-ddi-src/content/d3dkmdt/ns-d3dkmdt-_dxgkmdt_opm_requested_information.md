---
UID: NS:d3dkmdt._DXGKMDT_OPM_REQUESTED_INFORMATION
title: _DXGKMDT_OPM_REQUESTED_INFORMATION
author: windows-driver-content
description: The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the DxgkDdiOPMGetInformation or DxgkDdiOPMGetCOPPCompatibleInformation function.
old-location: display\dxgkmdt_opm_requested_information.htm
old-project: display
ms.assetid: c483786a-be8c-4ae3-a48c-45064ce81939
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKMDT_OPM_REQUESTED_INFORMATION, PDXGKMDT_OPM_REQUESTED_INFORMATION, DmStructs_671b07eb-3d44-4c06-863a-8bd74f10ee4b.xml, *PDXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/PDXGKMDT_OPM_REQUESTED_INFORMATION, display.dxgkmdt_opm_requested_information, DXGKMDT_OPM_REQUESTED_INFORMATION structure [Display Devices], d3dkmdt/DXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION, PDXGKMDT_OPM_REQUESTED_INFORMATION structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmdt.h
apiname: 
-	DXGKMDT_OPM_REQUESTED_INFORMATION
product: Windows
targetos: Windows
req.typenames: *PDXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION
---

# _DXGKMDT_OPM_REQUESTED_INFORMATION structure


## -description


The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.


## -syntax


````
typedef struct _DXGKMDT_OPM_REQUESTED_INFORMATION {
  DXGKMDT_OPM_OMAC omac;
  ULONG            cbRequestedInformationSize;
  BYTE             abRequestedInformation[DXGKMDT_OPM_REQUESTED_INFORMATION_SIZE];
} DXGKMDT_OPM_REQUESTED_INFORMATION, *PDXGKMDT_OPM_REQUESTED_INFORMATION;
````


## -struct-fields




### -field omac

A <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a> structure that contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. For more information about OMAC, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70417">OMAC-1 algorithm</a>. The OMAC-1 parameters that OPM and COPP use are:

<i>E</i> = AES (Advanced Encryption Standard)

<i>t</i> = 128 bits

<i>K</i> = The 128-bit key that the display miniport driver receives when <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> is called.

<i>n</i> = 128 bits 

For information about AES, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. 


### -field cbRequestedInformationSize

The size, in bytes, of the valid data that the <b>abRequestedInformation</b> member points to. 


### -field abRequestedInformation

A 4076-byte array that specifies the information that is retrieved from a protected output object.

To return the requested information, the display miniport driver should cast <b>abRequestedInformation</b> to one of the following structures, depending on the GUID that was specified in the <b>guidInformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> or <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter of <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> or <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> points to. As an example, the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUID indicates the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a> structure.
<table>
<tr>
<th>GUID</th>
<th>Structure for retrieved information</th>
</tr>
<tr>
<td>

<dl>
<dt>DXGKMDT_OPM_GET_CONNECTOR_TYPE, DXGKMDT_OPM_GET_SUPPORTED_PROTECTION_TYPES, DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ADAPTER_BUS_TYPE, </dt>
<dt>DXGKMDT_OPM_GET_DVI_CHARACTERISTICS, or DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION</dt>
</dl>


</td>
<td>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_ACTUAL_OUTPUT_FORMAT

</td>
<td>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_OUTPUT_ID

</td>
<td>
Supported in Windows 7 and later versions.


<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_output_id.md">DXGKMDT_OPM_OUTPUT_ID</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING

</td>
<td>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>


</td>
</tr>
<tr>
<td>
DXGKMDT_OPM_GET_CONNECTED

_HDCP_DEVICE_INFORMATION

</td>
<td>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>


</td>
</tr>
</table> 


## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_output_id.md">DXGKMDT_OPM_OUTPUT_ID</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_REQUESTED_INFORMATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

