---
UID: NS:d3dkmdt._DXGKMDT_OPM_REQUESTED_INFORMATION
title: DXGKMDT_OPM_REQUESTED_INFORMATION (d3dkmdt.h)
description: The DXGKMDT_OPM_REQUESTED_INFORMATION structure contains information that was requested in a call to the DxgkDdiOPMGetInformation or DxgkDdiOPMGetCOPPCompatibleInformation function.
old-location: display\dxgkmdt_opm_requested_information.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGKMDT_OPM_REQUESTED_INFORMATION structure"]
ms.keywords: "*PDXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION, DXGKMDT_OPM_REQUESTED_INFORMATION structure [Display Devices], DmStructs_671b07eb-3d44-4c06-863a-8bd74f10ee4b.xml, PDXGKMDT_OPM_REQUESTED_INFORMATION, PDXGKMDT_OPM_REQUESTED_INFORMATION structure pointer [Display Devices], _DXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/DXGKMDT_OPM_REQUESTED_INFORMATION, d3dkmdt/PDXGKMDT_OPM_REQUESTED_INFORMATION, display.dxgkmdt_opm_requested_information"
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
 - _DXGKMDT_OPM_REQUESTED_INFORMATION
 - PDXGKMDT_OPM_REQUESTED_INFORMATION
 - DXGKMDT_OPM_REQUESTED_INFORMATION
---

# DXGKMDT_OPM_REQUESTED_INFORMATION structure

## -description

The **DXGKMDT_OPM_REQUESTED_INFORMATION** structure contains information that was requested in a call to the [*DxgkDdiOPMGetInformation*](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md) or [*DxgkDdiOPMGetCOPPCompatibleInformation*](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) function.

## -struct-fields

### -field omac

A [**DXGKMDT_OPM_OMAC**](ns-d3dkmdt-_dxgkmdt_opm_omac.md) structure that contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. For more information about OMAC, see the [OMAC-1 algorithm](https://go.microsoft.com/fwlink/p/?linkid=70417). The OMAC-1 parameters that OPM and COPP use are:

*E* = AES (Advanced Encryption Standard)

*t* = 128 bits

*K* = The 128-bit key that the display miniport driver receives when [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](../dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) is called.

*n* = 128 bits

For information about AES, see the [RSA Laboratories](https://www.rsa.com) website.

### -field cbRequestedInformationSize

The size, in bytes, of the valid data that the **abRequestedInformation** member points to.

### -field abRequestedInformation

A 4076-byte array that specifies the information that is retrieved from a protected output object.

To return the requested information, the display miniport driver should cast **abRequestedInformation** to one of the following structures, depending on the GUID that was specified in the **guidInformation** member of the [**DXGKMDT_OPM_GET_INFO_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md) or [**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md) structure that the **Parameters** parameter of [*DxgkDdiOPMGetInformation*](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md) or /dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information points to. As an example, the DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUID indicates the [**DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md) structure.

| GUID | Structure for retrieved information |
| ---- | ----------------------------------- |
| DXGKMDT_OPM_GET_CONNECTOR_TYPE, DXGKMDT_OPM_GET_SUPPORTED_PROTECTION_TYPES, DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL, DXGKMDT_OPM_GET_ADAPTER_BUS_TYPE, DXGKMDT_OPM_GET_DVI_CHARACTERISTICS or DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION | [**DXGKMDT_OPM_STANDARD_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_standard_information.md)  |
| DXGKMDT_OPM_GET_ACTUAL_OUTPUT_FORMAT | [**DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT**](ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md)  |
| DXGKMDT_OPM_GET_OUTPUT_ID | [**DXGKMDT_OPM_OUTPUT_ID**](ns-d3dkmdt-_dxgkmdt_opm_output_id.md). Supported in Windows 7 and later versions. |
| DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING | [**DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING**](ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md)  |
| DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION | [**DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md)  |

## -see-also

[**DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING**](ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md)

[**DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT**](ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md)

[**DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md)

[**DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_copp_compatible_get_info_parameters.md)

[**DXGKMDT_OPM_GET_INFO_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md)

[**DXGKMDT_OPM_OMAC**](ns-d3dkmdt-_dxgkmdt_opm_omac.md)

[**DXGKMDT_OPM_OUTPUT_ID**](ns-d3dkmdt-_dxgkmdt_opm_output_id.md)

[**DXGKMDT_OPM_STANDARD_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_standard_information.md)

[*DxgkDdiOPMGetCOPPCompatibleInformation*](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md)

[*DxgkDdiOPMGetInformation*](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md)
