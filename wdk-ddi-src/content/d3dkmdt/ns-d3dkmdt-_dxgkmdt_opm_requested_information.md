---
UID: NS:d3dkmdt._DXGKMDT_OPM_REQUESTED_INFORMATION
title: _DXGKMDT_OPM_REQUESTED_INFORMATION (d3dkmdt.h)
description: The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the DxgkDdiOPMGetInformation or DxgkDdiOPMGetCOPPCompatibleInformation function.
old-location: display\dxgkmdt_opm_requested_information.htm
tech.root: display
ms.assetid: c483786a-be8c-4ae3-a48c-45064ce81939
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_REQUESTED_INFORMATION structure"]
ms.keywords: "*PDXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION structure [Display Devices], DmStructs_671b07eb-3d44-4c06-863a-8bd74f10ee4b.xml, PDXGKMDT_OPM_REQUESTED_INFORMATION, PDXGKMDT_OPM_REQUESTED_INFORMATION structure pointer [Display Devices], _DXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/DXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/PDXGKMDT_OPM_REQUESTED_INFORMATION, display.dxgkmdt_opm_requested_information"
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
targetos: Windows
req.typenames: DXGKMDT_OPM_REQUESTED_INFORMATION, *PDXGKMDT_OPM_REQUESTED_INFORMATION
f1_keywords:
 - _DXGKMDT_OPM_REQUESTED_INFORMATION
 - d3dkmdt/_DXGKMDT_OPM_REQUESTED_INFORMATION
 - PDXGKMDT_OPM_REQUESTED_INFORMATION
 - d3dkmdt/PDXGKMDT_OPM_REQUESTED_INFORMATION
 - DXGKMDT_OPM_REQUESTED_INFORMATION
 - d3dkmdt/DXGKMDT_OPM_REQUESTED_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DXGKMDT_OPM_REQUESTED_INFORMATION
---

# _DXGKMDT_OPM_REQUESTED_INFORMATION structure


## -description

The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.

## -struct-fields

### -field omac

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_omac">DXGKMDT_OPM_OMAC</a> structure that contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. For more information about OMAC, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=70417">OMAC-1 algorithm</a>. The OMAC-1 parameters that OPM and COPP use are:

<i>E</i> = AES (Advanced Encryption Standard)

<i>t</i> = 128 bits

<i>K</i> = The 128-bit key that the display miniport driver receives when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> is called.

<i>n</i> = 128 bits 

For information about AES, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website.

### -field cbRequestedInformationSize

The size, in bytes, of the valid data that the <b>abRequestedInformation</b> member points to.

### -field abRequestedInformation

A 4076-byte array that specifies the information that is retrieved from a protected output object.

To return the requested information, the display miniport driver should cast <b>abRequestedInformation</b> to one of the following structures, depending on the GUID that was specified in the <b>guidInformation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a> points to. As an example, the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUID indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a> structure.

| **GUID** | **Structure for retrieved information** | 
|:--|:--|
| DXGKMDT_OPM_GET_CONNECTOR_TYPE, DXGKMDT_OPM_GET_SUPPORTED_PROTECTION_TYPES, DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ADAPTER_BUS_TYPE, [DXGKMDT_OPM_STANDARD_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information)  |
DXGKMDT_OPM_GET_DVI_CHARACTERISTICS, or DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION |
| DXGKMDT_OPM_GET_ACTUAL_OUTPUT_FORMAT | [DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_actual_output_format)  |
| DXGKMDT_OPM_GET_OUTPUT_ID | Supported in Windows 7 and later versions.
[DXGKMDT_OPM_OUTPUT_ID](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_output_id)  | 
| DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING | [DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling)  |
| DXGKMDT_OPM_GET_CONNECTED [DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information)  |
_HDCP_DEVICE_INFORMATION |

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_actual_output_format">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_omac">DXGKMDT_OPM_OMAC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_output_id">DXGKMDT_OPM_OUTPUT_ID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>

