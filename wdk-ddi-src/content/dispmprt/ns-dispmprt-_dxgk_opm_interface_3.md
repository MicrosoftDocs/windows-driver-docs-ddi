---
UID: NS:dispmprt._DXGK_OPM_INTERFACE_3
title: _DXGK_OPM_INTERFACE_3 (dispmprt.h)
description: The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface_3.htm
tech.root: display
ms.assetid: 0BD6BA91-7F46-482B-B808-DEB8A23A0B84
ms.date: 08/21/2020
keywords: ["DXGK_OPM_INTERFACE_3 structure"]
ms.keywords: "*PDXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3 structure [Display Devices], PDXGK_OPM_INTERFACE_3, PDXGK_OPM_INTERFACE_3 structure pointer [Display Devices], _DXGK_OPM_INTERFACE_3, display.dxgk_opm_interface_3, dispmprt/DXGK_OPM_INTERFACE_3, dispmprt/PDXGK_OPM_INTERFACE_3"
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: DXGK_OPM_INTERFACE_3, *PDXGK_OPM_INTERFACE_3
f1_keywords:
 - _DXGK_OPM_INTERFACE_3
 - dispmprt/_DXGK_OPM_INTERFACE_3
 - PDXGK_OPM_INTERFACE_3
 - dispmprt/PDXGK_OPM_INTERFACE_3
 - DXGK_OPM_INTERFACE_3
 - dispmprt/DXGK_OPM_INTERFACE_3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - DXGK_OPM_INTERFACE_3
---

# DXGK_OPM_INTERFACE_3 structure


## -description

The **DXGK_OPM_INTERFACE_3** structure contains pointers to functions in the [Output Protection Manager (OPM) Interface](/windows-hardware/drivers/display/supporting-output-protection-manager), which is implemented by the display miniport driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The **Version** member must be set to DXGK_OPM_INTERFACE_VERSION_3, which is defined in *Dispmprt.h*.

### -field Context

A pointer to a private context block. **Context** must be set to **NULL**.

### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure.

### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure.

### -field DxgkDdiOPMGetCertificateSize

A pointer to the display miniport driver's [**DxgkDdiOPMGetCertificateSize**](nc-dispmprt-dxgkddi_opm_get_certificate_size.md) function.

### -field DxgkDdiOPMGetCertificate

A pointer to the display miniport driver's [**DxgkDdiOPMGetCertificate**](nc-dispmprt-dxgkddi_opm_get_certificate.md) function.

### -field DxgkDdiOPMCreateProtectedOutput

A pointer to the display miniport driver's [**DxgkDdiOPMCreateProtectedOutput**](nc-dispmprt-dxgkddi_opm_create_protected_output.md) function.

### -field DxgkDdiOPMGetRandomNumber

A pointer to the display miniport driver's [**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md) function.

### -field DxgkDdiOPMSetSigningKeyAndSequenceNumbers

A pointer to the display miniport driver's [**DxgkDdiOPMSetSigningKeyAndSequenceNumbers**](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) function.

### -field DxgkDdiOPMGetInformation

A pointer to the display miniport driver's [**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md) function.

### -field DxgkDdiOPMGetCOPPCompatibleInformation

A pointer to the display miniport driver's [**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) function.

### -field DxgkDdiOPMConfigureProtectedOutput

A pointer to the display miniport driver's [**DxgkDdiOPMConfigureProtectedOutput**](nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function.

### -field DxgkDdiOPMDestroyProtectedOutput

A pointer to the display miniport driver's [**DxgkDdiOPMDestroyProtectedOutput**](nc-dispmprt-dxgkddi_opm_destroy_protected_output.md) function.

### -field DxgkDdiOPMCreateProtectedOutputNonLocalDisplay

A pointer to the display miniport driver's [**DxgkDdiOPMCreateProtectedOutputNonLocalDisplay**](nc-dispmprt-dxgkddi_opm_create_protected_output_nonlocal_display.md) function.

### -field DxgkDdiOPMSetSrmList

A pointer to the display miniport driver's [**DxgkDdiOPMSetSrmList**](nc-dispmprt-dxgkddi_opm_set_srm_list.md) function.

### -field DxgkDdiOPMGetSrmListVersion

A pointer to the display miniport driver's [**DxgkDdiOPMGetSrmListVersion**](nc-dispmprt-dxgkddi_opm_get_srm_list_version.md) function.