---
UID: NS:dispmprt._DXGK_OPM_INTERFACE
title: "_DXGK_OPM_INTERFACE"
author: windows-driver-content
description: The DXGK_OPM_INTERFACE structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_opm_interface.htm
old-project: display
ms.assetid: 6ae1d9a8-db9a-460d-b258-222a2bd96265
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_OPM_INTERFACE structure [Display Devices], DXGK_OPM_INTERFACE, _DXGK_OPM_INTERFACE, *PDXGK_OPM_INTERFACE, dispmprt/DXGK_OPM_INTERFACE, display.dxgk_opm_interface, dispmprt/PDXGK_OPM_INTERFACE, PDXGK_OPM_INTERFACE structure pointer [Display Devices], PDXGK_OPM_INTERFACE, DmStructs_e1644da8-220d-470a-b9b9-f23ba7e1c4f6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dispmprt.h
apiname:
-	DXGK_OPM_INTERFACE
product: Windows
targetos: Windows
req.typenames: "*PDXGK_OPM_INTERFACE, DXGK_OPM_INTERFACE"
---

# _DXGK_OPM_INTERFACE structure


## -description


The DXGK_OPM_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/8dc171f7-76ca-4e1a-865e-7dcb6ab9a2e9">Output Protection Manager (OPM) Interface</a>, which is implemented by the display miniport driver.


## -syntax


````
typedef struct _DXGK_OPM_INTERFACE {
  USHORT                                           Size;
  USHORT                                           Version;
  PVOID                                            Context;
  PINTERFACE_REFERENCE                             InterfaceReference;
  PINTERFACE_DEREFERENCE                           InterfaceDereference;
  DXGKDDI_OPM_GET_CERTIFICATE_SIZE                 DxgkDdiOPMGetCertificateSize;
  DXGKDDI_OPM_GET_CERTIFICATE                      DxgkDdiOPMGetCertificate;
  DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT              DxgkDdiOPMCreateProtectedOutput;
  DXGKDDI_OPM_GET_RANDOM_NUMBER                    DxgkDdiOPMGetRandomNumber;
  DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS DxgkDdiOPMSetSigningKeyAndSequenceNumbers;
  DXGKDDI_OPM_GET_INFORMATION                      DxgkDdiOPMGetInformation;
  DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION      DxgkDdiOPMGetCOPPCompatibleInformation;
  DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT           DxgkDdiOPMConfigureProtectedOutput;
  DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT             DxgkDdiOPMDestroyProtectedOutput;
} DXGK_OPM_INTERFACE, *PDXGK_OPM_INTERFACE;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

A positive integer that indicates the version number of the OPM interface that is implemented by the display miniport driver. The <b>Version</b> member must be set to DXGK_OPM_INTERFACE_VERSION_1, which is defined in Dispmprt.h.


### -field Context

A pointer to a private context block. <b>Context</b> must be set to <b>NULL</b>.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver. For more information about the operation of an interface reference function, see the Remarks section of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver. For more information about the operation of an interface dereference function, see the Remarks section of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.


### -field DxgkDdiOPMGetCertificateSize

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a> function.


### -field DxgkDdiOPMGetCertificate

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate.md">DxgkDdiOPMGetCertificate</a> function.


### -field DxgkDdiOPMCreateProtectedOutput

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function.


### -field DxgkDdiOPMGetRandomNumber

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a> function.


### -field DxgkDdiOPMSetSigningKeyAndSequenceNumbers

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function.


### -field DxgkDdiOPMGetInformation

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function.


### -field DxgkDdiOPMGetCOPPCompatibleInformation

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> function.


### -field DxgkDdiOPMConfigureProtectedOutput

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function.


### -field DxgkDdiOPMDestroyProtectedOutput

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMDestroyProtectedOutput</a> function.


## -remarks


A kernel-mode component that must use the OPM interface initiates a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function to retrieve the interface.

For more information on how to use this structure with the OPM interface, see <a href="https://msdn.microsoft.com/84218245-f5f3-4a6f-88ed-9cd5db224e30">Retrieving the OPM DDI</a>.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_random_number.md">DxgkDdiOPMGetRandomNumber</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate.md">DxgkDdiOPMGetCertificate</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_destroy_protected_output.md">DxgkDdiOPMDestroyProtectedOutput</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_OPM_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

