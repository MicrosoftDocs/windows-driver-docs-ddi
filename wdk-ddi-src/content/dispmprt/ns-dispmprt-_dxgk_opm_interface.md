---
UID: NS:dispmprt._DXGK_OPM_INTERFACE
title: _DXGK_OPM_INTERFACE (dispmprt.h)
description: The DXGK_OPM_INTERFACE structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface.htm
tech.root: display
ms.assetid: 6ae1d9a8-db9a-460d-b258-222a2bd96265
ms.date: 05/10/2018
keywords: ["_DXGK_OPM_INTERFACE structure"]
ms.keywords: "*PDXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE structure [Display Devices], DmStructs_e1644da8-220d-470a-b9b9-f23ba7e1c4f6.xml, PDXGK_OPM_INTERFACE, PDXGK_OPM_INTERFACE structure pointer [Display Devices], _DXGK_OPM_INTERFACE, display.dxgk_opm_interface, dispmprt/DXGK_OPM_INTERFACE, dispmprt/PDXGK_OPM_INTERFACE"
f1_keywords:
 - "dispmprt/DXGK_OPM_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dispmprt.h
api_name:
- DXGK_OPM_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: DXGK_OPM_INTERFACE, *PDXGK_OPM_INTERFACE
---

# _DXGK_OPM_INTERFACE structure


## -description


The DXGK_OPM_INTERFACE structure contains pointers to functions in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Output Protection Manager (OPM) Interface</a>, which is implemented by the display miniport driver.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The <b>Version</b> member must be set to DXGK_OPM_INTERFACE_VERSION_1, which is defined in Dispmprt.h.


### -field Context

A pointer to a private context block. <b>Context</b> must be set to <b>NULL</b>.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.


### -field DxgkDdiOPMGetCertificateSize

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a> function.


### -field DxgkDdiOPMGetCertificate

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate">DxgkDdiOPMGetCertificate</a> function.


### -field DxgkDdiOPMCreateProtectedOutput

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a> function.


### -field DxgkDdiOPMGetRandomNumber

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_random_number">DxgkDdiOPMGetRandomNumber</a> function.


### -field DxgkDdiOPMSetSigningKeyAndSequenceNumbers

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function.


### -field DxgkDdiOPMGetInformation

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> function.


### -field DxgkDdiOPMGetCOPPCompatibleInformation

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.


### -field DxgkDdiOPMConfigureProtectedOutput

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a> function.


### -field DxgkDdiOPMDestroyProtectedOutput

A pointer to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output">DxgkDdiOPMDestroyProtectedOutput</a> function.


## -remarks



A kernel-mode component that must use the OPM interface initiates a call to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface">DxgkDdiQueryInterface</a> function to retrieve the interface.

For more information on how to use this structure with the OPM interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/retrieving-the-opm-ddi">Retrieving the OPM DDI</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_destroy_protected_output">DxgkDdiOPMDestroyProtectedOutput</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate">DxgkDdiOPMGetCertificate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_certificate_size">DxgkDdiOPMGetCertificateSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_random_number">DxgkDdiOPMGetRandomNumber</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface">DxgkDdiQueryInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>
 

 

