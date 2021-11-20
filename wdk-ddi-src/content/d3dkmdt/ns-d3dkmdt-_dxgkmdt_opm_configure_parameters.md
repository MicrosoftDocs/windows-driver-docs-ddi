---
UID: NS:d3dkmdt._DXGKMDT_OPM_CONFIGURE_PARAMETERS
title: DXGKMDT_OPM_CONFIGURE_PARAMETERS (d3dkmdt.h)
description: The DXGKMDT_OPM_CONFIGURE_PARAMETERS structure contains parameters that are used to configure a protected output object in a call to the DxgkDdiOPMConfigureProtectedOutput function.
old-location: display\dxgkmdt_opm_configure_parameters.htm
tech.root: display
ms.date: 11/18/2021
keywords: ["DXGKMDT_OPM_CONFIGURE_PARAMETERS structure"]
ms.keywords: "*PDXGKMDT_OPM_CONFIGURE_PARAMETERS, DXGKMDT_OPM_CONFIGURE_PARAMETERS, DXGKMDT_OPM_CONFIGURE_PARAMETERS structure [Display Devices], DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING, DXGKMDT_OPM_SET_HDCP_SRM, DXGKMDT_OPM_SET_PROTECTION_LEVEL or DXGKMDT_OPM_SET_PROTECTION_LEVEL_ACCORDING_TO_CSS_DVD, DmStructs_98db66f6-39e1-4e08-83c5-ead1c527302f.xml, PDXGKMDT_OPM_CONFIGURE_PARAMETERS, PDXGKMDT_OPM_CONFIGURE_PARAMETERS structure pointer [Display Devices], _DXGKMDT_OPM_CONFIGURE_PARAMETERS, d3dkmdt/DXGKMDT_OPM_CONFIGURE_PARAMETERS, d3dkmdt/PDXGKMDT_OPM_CONFIGURE_PARAMETERS, display.dxgkmdt_opm_configure_parameters"
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
req.typenames: DXGKMDT_OPM_CONFIGURE_PARAMETERS, *PDXGKMDT_OPM_CONFIGURE_PARAMETERS
f1_keywords:
 - _DXGKMDT_OPM_CONFIGURE_PARAMETERS
 - d3dkmdt/_DXGKMDT_OPM_CONFIGURE_PARAMETERS
 - PDXGKMDT_OPM_CONFIGURE_PARAMETERS
 - d3dkmdt/PDXGKMDT_OPM_CONFIGURE_PARAMETERS
 - DXGKMDT_OPM_CONFIGURE_PARAMETERS
 - d3dkmdt/DXGKMDT_OPM_CONFIGURE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKMDT_OPM_CONFIGURE_PARAMETERS
 - PDXGKMDT_OPM_CONFIGURE_PARAMETERS
 - DXGKMDT_OPM_CONFIGURE_PARAMETERS
---

# DXGKMDT_OPM_CONFIGURE_PARAMETERS structure

## -description

The **DXGKMDT_OPM_CONFIGURE_PARAMETERS** structure contains parameters that are used to configure a protected output object in a call to the [*DxgkDdiOPMConfigureProtectedOutput*](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function.

## -struct-fields

### -field omac

A [**DXGKMDT_OPM_OMAC**](ns-d3dkmdt-_dxgkmdt_opm_omac.md) structure that contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. For more information about OMAC, see the [OMAC-1 algorithm](https://go.microsoft.com/fwlink/p/?linkid=70417). The OMAC-1 parameters that OPM and COPP use are:

*E* = AES (Advanced Encryption Standard)

*t* = 128 bits

*K* = The 128-bit key the display miniport driver receives when [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](../dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) is called.

*n* = 128 bits

For information about AES, see the [RSA Laboratories](https://www.rsa.com) website.

### -field guidSetting

The GUID that is used to configure the protected output object. **guidSetting** can be set to one of the following GUIDs:

* DXGKMDT_OPM_SET_PROTECTION_LEVEL
* DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING
* DXGKMDT_OPM_SET_HDCP_SRM
* DXGKMDT_OPM_SET_PROTECTION_LEVEL_ACCORDING_TO_CSS_DVD. Supported in Windows 7 and later versions.

### -field ulSequenceNumber

A sequence number. For the [*DxgkDdiOPMConfigureProtectedOutput*](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function to process a configure request, the value in **ulSequenceNumber** must match the current 4-byte sequence number that the display miniport driver stores. If a match is not detected, *DxgkDdiOPMConfigureProtectedOutput* returns an error code. If a match is detected, *DxgkDdiOPMConfigureProtectedOutput* increments the stored sequence number before returning. The initial 4-byte sequence number is part of the 256-byte array that the *EncryptedParameters* parameter of the [*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](../dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) function points to.

### -field cbParametersSize

The size, in bytes, of the valid configuration data that the **abParameters** member points to.

### -field abParameters

A 4056-byte array that specifies how to configure the protected output object.

The **abParameters** parameter is cast to one of the following structures that contains the configuration information, depending on the GUID that is specified in the **guidSetting** member of DXGKMDT_OPM_CONFIGURE_PARAMETERS that the *Parameters* parameter of [*DxgkDdiOPMConfigureProtectedOutput*](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) points to.

These are possible GUIDs and structures for configuration information:

| GUID | Structure for retrieved information |
| ---- | ----------------------------------- |
| DXGKMDT_OPM_SET_PROTECTION_LEVEL or DXGKMDT_OPM_SET_PROTECTION_LEVEL_ACCORDING_TO_CSS_DVD | [**DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md) |
| DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING | [**DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.md) |
| DXGKMDT_OPM_SET_HDCP_SRM | [**DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_hdcp_srm_parameters.md) |

## -see-also

[**DXGKMDT_OPM_OMAC**](ns-d3dkmdt-_dxgkmdt_opm_omac.md)

[**DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.md)

[**DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_hdcp_srm_parameters.md)

[**DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md)

[*DxgkDdiOPMConfigureProtectedOutput*](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md)

[*DxgkDdiOPMSetSigningKeyAndSequenceNumbers*](../dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md)
