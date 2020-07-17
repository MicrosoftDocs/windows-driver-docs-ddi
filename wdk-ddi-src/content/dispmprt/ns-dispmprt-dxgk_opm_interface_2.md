---
UID: NS:dispmprt._DXGK_OPM_INTERFACE_2
title: DXGK_OPM_INTERFACE_2
ms.date: 03/24/2020
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
 - DXGK_OPM_INTERFACE_2
f1_keywords:
 - dispmprt/_DXGK_OPM_INTERFACE_2
 - dispmprt/DXGK_OPM_INTERFACE_2
 - ""
dev_langs:
 - c++
---

# DXGK_OPM_INTERFACE_2 structure

## -description

The DXGK_OPM_INTERFACE_2 structure contains pointers to functions in the [Output Protection Manager (OPM) Interface](https://docs.microsoft.com/windows-hardware/drivers/ddi/index), which is implemented by the display miniport driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The **Version** member must be set to DXGK_OPM_INTERFACE_VERSION_2, which is defined in Dispmprt.h.

### -field Context

A pointer to a private context block. **Context** must be set to **NULL**.

### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the [**INTERFACE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface) structure.

### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the [**INTERFACE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface) structure.

### -field DxgkDdiOPMGetCertificateSize

A pointer to the display miniport driver's [**DxgkDdiOPMGetCertificateSize**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size) function.

### -field DxgkDdiOPMGetCertificate

A pointer to the display miniport driver's [**DxgkDdiOPMGetCertificate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate) function.

### -field DxgkDdiOPMCreateProtectedOutput

A pointer to the display miniport driver's [**DxgkDdiOPMCreateProtectedOutput**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output) function.

### -field DxgkDdiOPMGetRandomNumber

A pointer to the display miniport driver's [**DxgkDdiOPMGetRandomNumber**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_random_number) function.

### -field DxgkDdiOPMSetSigningKeyAndSequenceNumbers

A pointer to the display miniport driver's [**DxgkDdiOPMSetSigningKeyAndSequenceNumbers**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers) function.

### -field DxgkDdiOPMGetInformation

A pointer to the display miniport driver's [**DxgkDdiOPMGetInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information) function.

### -field DxgkDdiOPMGetCOPPCompatibleInformation

A pointer to the display miniport driver's [**DxgkDdiOPMGetCOPPCompatibleInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information) function.

### -field DxgkDdiOPMConfigureProtectedOutput

A pointer to the display miniport driver's [**DxgkDdiOPMConfigureProtectedOutput**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output) function.

### -field DxgkDdiOPMDestroyProtectedOutput

A pointer to the display miniport driver's [**DxgkDdiOPMDestroyProtectedOutput**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output) function.

### -field DxgkDdiOPMCreateProtectedOutputNonLocalDisplay

A pointer to the display miniport driver's [**DxgkDdiOPMCreateProtectedOutputNonLocalDisplay**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output) function.

## -remarks

A kernel-mode component that must use the OPM interface initiates a call to the display miniport driver's [**DxgkDdiQueryInterface**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface) function to retrieve the interface.

For more information on how to use this structure with the OPM interface, see [Retrieving the OPM DDI](https://docs.microsoft.com/windows-hardware/drivers/display/retrieving-the-opm-ddi).

## -see-also

[**DxgkDdiOPMConfigureProtectedOutput**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output)

[**DxgkDdiOPMCreateProtectedOutput**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output)

[**DxgkDdiOPMDestroyProtectedOutput**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output)

[**DxgkDdiOPMGetCOPPCompatibleInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information)

[**DxgkDdiOPMGetCertificate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate)

[**DxgkDdiOPMGetCertificateSize**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size)

[**DxgkDdiOPMGetInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information)

[**DxgkDdiOPMGetRandomNumber**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_random_number)

[**DxgkDdiOPMSetSigningKeyAndSequenceNumbers**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers)

[**DxgkDdiQueryInterface**](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface)

[**INTERFACE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface)
