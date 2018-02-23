---
UID: NS:d3dkmdt._DXGKMDT_OPM_ENCRYPTED_PARAMETERS
title: "_DXGKMDT_OPM_ENCRYPTED_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure contains data that is encrypted with the public key from an appropriate certificate.
old-location: display\dxgkmdt_opm_encrypted_parameters.htm
old-project: display
ms.assetid: 43aa91cb-584e-47b7-a6d4-2e95adf24a28
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DmStructs_760ebc6b-c03b-468d-b4b0-29faabd65cd1.xml, DXGKMDT_OPM_ENCRYPTED_PARAMETERS, d3dkmdt/PDXGKMDT_OPM_ENCRYPTED_PARAMETERS, *PDXGKMDT_OPM_ENCRYPTED_PARAMETERS, DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure [Display Devices], display.dxgkmdt_opm_encrypted_parameters, PDXGKMDT_OPM_ENCRYPTED_PARAMETERS structure pointer [Display Devices], _DXGKMDT_OPM_ENCRYPTED_PARAMETERS, d3dkmdt/DXGKMDT_OPM_ENCRYPTED_PARAMETERS, PDXGKMDT_OPM_ENCRYPTED_PARAMETERS
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
-	DXGKMDT_OPM_ENCRYPTED_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PDXGKMDT_OPM_ENCRYPTED_PARAMETERS, DXGKMDT_OPM_ENCRYPTED_PARAMETERS"
---

# _DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure


## -description


The DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure contains data that is encrypted with the public key from an appropriate certificate.


## -syntax


````
typedef struct _DXGKMDT_OPM_ENCRYPTED_PARAMETERS {
  BYTE abEncryptedParameters[DXGKMDT_OPM_ENCRYPTED_PARAMETERS_SIZE];
} DXGKMDT_OPM_ENCRYPTED_PARAMETERS, *PDXGKMDT_OPM_ENCRYPTED_PARAMETERS;
````


## -struct-fields




### -field abEncryptedParameters

A 256-byte array that comprises data that is encrypted with the public key from an appropriate certificate.


## -remarks



For more information about the certificates and algorithms that are used to encrypt the data in DXGKMDT_OPM_ENCRYPTED_PARAMETERS, see the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> reference page.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

