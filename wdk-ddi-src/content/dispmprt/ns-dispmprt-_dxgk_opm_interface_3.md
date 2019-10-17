---
UID: NS:dispmprt._DXGK_OPM_INTERFACE_3
title: _DXGK_OPM_INTERFACE_3 (dispmprt.h)
description: The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface_3.htm
tech.root: display
ms.assetid: 0BD6BA91-7F46-482B-B808-DEB8A23A0B84
ms.date: 05/10/2018
ms.keywords: "*PDXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3, DXGK_OPM_INTERFACE_3 structure [Display Devices], PDXGK_OPM_INTERFACE_3, PDXGK_OPM_INTERFACE_3 structure pointer [Display Devices], _DXGK_OPM_INTERFACE_3, display.dxgk_opm_interface_3, dispmprt/DXGK_OPM_INTERFACE_3, dispmprt/PDXGK_OPM_INTERFACE_3"
ms.topic: struct
f1_keywords:
 - "dispmprt/DXGK_OPM_INTERFACE_3"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_OPM_INTERFACE_3
product:
- Windows
targetos: Windows
req.typenames: DXGK_OPM_INTERFACE_3, *PDXGK_OPM_INTERFACE_3
---

# _DXGK_OPM_INTERFACE_3 structure


## -description


The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Output Protection Manager (OPM) Interface</a>, which is implemented by the display miniport driver.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The <b>Version</b> member must be set to DXGK_OPM_INTERFACE_VERSION_1, which is defined in Dispmprt.h.


### -field Context

A pointer to a private context block. <b>Context</b> must be set to <b>NULL</b>.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_interface">INTERFACE</a> structure.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_interface">INTERFACE</a> structure.


### -field DxgkDdiOPMGetCertificateSize

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a> function.


### -field DxgkDdiOPMGetCertificate

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate">DxgkDdiOPMGetCertificate</a> function.


### -field DxgkDdiOPMCreateProtectedOutput

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a> function.


### -field DxgkDdiOPMGetRandomNumber

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_random_number">DxgkDdiOPMGetRandomNumber</a> function.


### -field DxgkDdiOPMSetSigningKeyAndSequenceNumbers

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function.


### -field DxgkDdiOPMGetInformation

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> function.


### -field DxgkDdiOPMGetCOPPCompatibleInformation

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.


### -field DxgkDdiOPMConfigureProtectedOutput

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a> function.


### -field DxgkDdiOPMDestroyProtectedOutput

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output">DxgkDdiOPMDestroyProtectedOutput</a> function.


### -field DxgkDdiOPMCreateProtectedOutputNonLocalDisplay

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output">DxgkDdiOPMCreateProtectedOutputNonLocalDisplay</a> function.


### -field DxgkDdiOPMSetSrmList

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output">DxgkDdiOPMSetSrmList</a> function.


### -field DxgkDdiOPMGetSrmListVersion

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output">DxgkDdiOPMGetSrmListVersion</a> function.

