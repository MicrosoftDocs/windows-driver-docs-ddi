---
UID: NS:dispmprt._DXGK_OPM_INTERFACE
title: DXGK_OPM_INTERFACE (dispmprt.h)
description: The DXGK_OPM_INTERFACE structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface.htm
tech.root: display
ms.date: 11/19/2021
keywords: ["DXGK_OPM_INTERFACE structure"]
ms.keywords: "*PDXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE structure [Display Devices], DmStructs_e1644da8-220d-470a-b9b9-f23ba7e1c4f6.xml, PDXGK_OPM_INTERFACE, PDXGK_OPM_INTERFACE structure pointer [Display Devices], _DXGK_OPM_INTERFACE, display.dxgk_opm_interface, dispmprt/DXGK_OPM_INTERFACE, dispmprt/PDXGK_OPM_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.typenames: DXGK_OPM_INTERFACE, *PDXGK_OPM_INTERFACE
f1_keywords:
 - _DXGK_OPM_INTERFACE
 - dispmprt/_DXGK_OPM_INTERFACE
 - PDXGK_OPM_INTERFACE
 - dispmprt/PDXGK_OPM_INTERFACE
 - DXGK_OPM_INTERFACE
 - dispmprt/DXGK_OPM_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dispmprt.h
api_name:
 - _DXGK_OPM_INTERFACE
 - PDXGK_OPM_INTERFACE
 - DXGK_OPM_INTERFACE
---

# DXGK_OPM_INTERFACE structure

## -description

The **DXGK_OPM_INTERFACE** structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The **Version** member must be set to DXGK_OPM_INTERFACE_VERSION_1, which is defined in *Dispmprt.h*.

### -field Context

A pointer to a private context block. **Context** must be set to NULL.

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

## -remarks

A kernel-mode component that must use the OPM interface initiates a call to the display miniport driver's [**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md) function to retrieve the interface.

For more information on how to use this structure with the OPM interface, see [Retrieving the OPM DDI](/windows-hardware/drivers/display/retrieving-the-opm-ddi).
