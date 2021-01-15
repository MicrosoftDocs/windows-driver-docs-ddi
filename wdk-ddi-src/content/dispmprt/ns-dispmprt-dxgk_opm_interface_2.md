---
UID: NS:dispmprt._DXGK_OPM_INTERFACE_2
title: DXGK_OPM_INTERFACE_2
ms.date: 08/21/2020
ms.topic: language-reference
targetos: Windows
description: The DXGK_OPM_INTERFACE_2 structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_OPM_INTERFACE_2, *PDXGK_OPM_INTERFACE_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_OPM_INTERFACE_2
 - PDXGK_OPM_INTERFACE_2
 - DXGK_OPM_INTERFACE_2
f1_keywords:
 - _DXGK_OPM_INTERFACE_2
 - dispmprt/_DXGK_OPM_INTERFACE_2
 - PDXGK_OPM_INTERFACE_2
 - dispmprt/PDXGK_OPM_INTERFACE_2
 - DXGK_OPM_INTERFACE_2
 - dispmprt/DXGK_OPM_INTERFACE_2
dev_langs:
 - c++
---

# DXGK_OPM_INTERFACE_2 structure


## -description

The **DXGK_OPM_INTERFACE_2** structure contains pointers to functions in the [Output Protection Manager (OPM) Interface](/windows-hardware/drivers/display/supporting-output-protection-manager), which is implemented by the display miniport driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The **Version** member must be set to DXGK_OPM_INTERFACE_VERSION_2, which is defined in *Dispmprt.h*.

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

## -remarks

A kernel-mode component that must use the OPM interface initiates a call to the display miniport driver's [**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md) function to retrieve the interface.

For more information on how to use this structure with the OPM interface, see [Retrieving the OPM DDI](/windows-hardware/drivers/display/retrieving-the-opm-ddi).

## -see-also

[**DxgkDdiOPMConfigureProtectedOutput**](nc-dispmprt-dxgkddi_opm_configure_protected_output.md)

[**DxgkDdiOPMCreateProtectedOutput**](nc-dispmprt-dxgkddi_opm_create_protected_output.md)

[**DxgkDdiOPMCreateProtectedOutputNonLocalDisplay**](nc-dispmprt-dxgkddi_opm_create_protected_output_nonlocal_display.md)

[**DxgkDdiOPMDestroyProtectedOutput**](nc-dispmprt-dxgkddi_opm_destroy_protected_output.md)

[**DxgkDdiOPMGetCOPPCompatibleInformation**](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md)

[**DxgkDdiOPMGetCertificate**](nc-dispmprt-dxgkddi_opm_get_certificate.md)

[**DxgkDdiOPMGetCertificateSize**](nc-dispmprt-dxgkddi_opm_get_certificate_size.md)

[**DxgkDdiOPMGetInformation**](nc-dispmprt-dxgkddi_opm_get_information.md)

[**DxgkDdiOPMGetRandomNumber**](nc-dispmprt-dxgkddi_opm_get_random_number.md)

[**DxgkDdiOPMSetSigningKeyAndSequenceNumbers**](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md)

[**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md)

[**INTERFACE**](../wdm/ns-wdm-_interface.md)

