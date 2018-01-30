---
UID: NS:d3dkmdt._DXGKMDT_OPM_CONFIGURE_PARAMETERS
title: "_DXGKMDT_OPM_CONFIGURE_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_CONFIGURE_PARAMETERS structure contains parameters that are used to configure a protected output object in a call to the DxgkDdiOPMConfigureProtectedOutput function.
old-location: display\dxgkmdt_opm_configure_parameters.htm
old-project: display
ms.assetid: 7f9a4770-c30d-41ae-bd46-dce106b1811d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_98db66f6-39e1-4e08-83c5-ead1c527302f.xml, DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING, PDXGKMDT_OPM_CONFIGURE_PARAMETERS, d3dkmdt/PDXGKMDT_OPM_CONFIGURE_PARAMETERS, display.dxgkmdt_opm_configure_parameters, DXGKMDT_OPM_SET_PROTECTION_LEVEL or DXGKMDT_OPM_SET_PROTECTION_LEVEL_ACCORDING_TO_CSS_DVD, DXGKMDT_OPM_SET_HDCP_SRM, DXGKMDT_OPM_CONFIGURE_PARAMETERS structure [Display Devices], DXGKMDT_OPM_CONFIGURE_PARAMETERS, _DXGKMDT_OPM_CONFIGURE_PARAMETERS, d3dkmdt/DXGKMDT_OPM_CONFIGURE_PARAMETERS, *PDXGKMDT_OPM_CONFIGURE_PARAMETERS, PDXGKMDT_OPM_CONFIGURE_PARAMETERS structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_CONFIGURE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_CONFIGURE_PARAMETERS, *PDXGKMDT_OPM_CONFIGURE_PARAMETERS
---

# _DXGKMDT_OPM_CONFIGURE_PARAMETERS structure


## -description


The DXGKMDT_OPM_CONFIGURE_PARAMETERS structure contains parameters that are used to configure a protected output object in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function.


## -syntax


````
typedef struct _DXGKMDT_OPM_CONFIGURE_PARAMETERS {
  DXGKMDT_OPM_OMAC omac;
  GUID             guidSetting;
  ULONG            ulSequenceNumber;
  ULONG            cbParametersSize;
  BYTE             abParameters[DXGKMDT_OPM_CONFIGURE_SETTING_DATA_SIZE];
} DXGKMDT_OPM_CONFIGURE_PARAMETERS, *PDXGKMDT_OPM_CONFIGURE_PARAMETERS;
````


## -struct-fields




### -field omac

A <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a> structure that contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity. For more information about OMAC, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70417">OMAC-1 algorithm</a>. The OMAC-1 parameters that OPM and COPP use are:

<i>E</i> = AES (Advanced Encryption Standard)

<i>t</i> = 128 bits

<i>K</i> = The 128-bit key the display miniport driver receives when <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> is called.

<i>n</i> = 128 bits 

For information about AES, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. 


### -field guidSetting

The GUID that is used to configure the protected output object. <b>guidSetting</b> can be set to one of the following GUIDs:
<ul>
<li>
DXGKMDT_OPM_SET_PROTECTION_LEVEL

</li>
<li>
DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING

</li>
<li>
DXGKMDT_OPM_SET_HDCP_SRM

</li>
<li>
Supported in Windows 7 and later versions.

DXGKMDT_OPM_SET_PROTECTION_LEVEL_ACCORDING_TO_CSS_DVD

</li>
</ul>

### -field ulSequenceNumber

A sequence number. For the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function to process a configure request, the value in <b>ulSequenceNumber</b> must match the current 4-byte sequence number that the display miniport driver stores. If a match is not detected, <i>DxgkDdiOPMConfigureProtectedOutput</i> returns an error code. If a match is detected, <i>DxgkDdiOPMConfigureProtectedOutput</i> increments the stored sequence number before returning. The initial 4-byte sequence number is part of the 256-byte array that the <i>EncryptedParameters</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> function points to. 


### -field cbParametersSize

The size, in bytes, of the valid configuration data that the <b>abParameters</b> member points to.


### -field abParameters

A 4056-byte array that specifies how to configure the protected output object.

The <b>abParameters</b> parameter is cast to one of the following structures that contains the configuration information, depending on the GUID that is specified in the <b>guidSetting</b> member of DXGKMDT_OPM_CONFIGURE_PARAMETERS that the <i>Parameters</i> parameter of <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> points to.


These are possible GUIDs and structures for configuration information:




#### DXGKMDT_OPM_SET_PROTECTION_LEVEL or DXGKMDT_OPM_SET_PROTECTION_LEVEL_ACCORDING_TO_CSS_DVD


<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



#### DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING


<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.md">DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS</a>



#### DXGKMDT_OPM_SET_HDCP_SRM


<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_hdcp_srm_parameters.md">DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS</a>



## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.md">DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_omac.md">DXGKMDT_OPM_OMAC</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_hdcp_srm_parameters.md">DXGKMDT_OPM_SET_HDCP_SRM_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_CONFIGURE_PARAMETERS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

