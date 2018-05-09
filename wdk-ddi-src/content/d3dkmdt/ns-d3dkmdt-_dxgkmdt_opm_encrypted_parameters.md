---
UID: NS:d3dkmdt._DXGKMDT_OPM_ENCRYPTED_PARAMETERS
title: "_DXGKMDT_OPM_ENCRYPTED_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure contains data that is encrypted with the public key from an appropriate certificate.
old-location: display\dxgkmdt_opm_encrypted_parameters.htm
old-project: display
ms.assetid: 43aa91cb-584e-47b7-a6d4-2e95adf24a28
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PDXGKMDT_OPM_ENCRYPTED_PARAMETERS, DXGKMDT_OPM_ENCRYPTED_PARAMETERS, DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure [Display Devices], DmStructs_760ebc6b-c03b-468d-b4b0-29faabd65cd1.xml, PDXGKMDT_OPM_ENCRYPTED_PARAMETERS, PDXGKMDT_OPM_ENCRYPTED_PARAMETERS structure pointer [Display Devices], _DXGKMDT_OPM_ENCRYPTED_PARAMETERS, d3dkmdt/DXGKMDT_OPM_ENCRYPTED_PARAMETERS, d3dkmdt/PDXGKMDT_OPM_ENCRYPTED_PARAMETERS, display.dxgkmdt_opm_encrypted_parameters"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_ENCRYPTED_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_ENCRYPTED_PARAMETERS, *PDXGKMDT_OPM_ENCRYPTED_PARAMETERS
---

# _DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure


## -description


The DXGKMDT_OPM_ENCRYPTED_PARAMETERS structure contains data that is encrypted with the public key from an appropriate certificate.


## -struct-fields




### -field abEncryptedParameters

A 256-byte array that comprises data that is encrypted with the public key from an appropriate certificate.


## -remarks



For more information about the certificates and algorithms that are used to encrypt the data in DXGKMDT_OPM_ENCRYPTED_PARAMETERS, see the <a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> reference page.




## -see-also




<a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>
 

 

