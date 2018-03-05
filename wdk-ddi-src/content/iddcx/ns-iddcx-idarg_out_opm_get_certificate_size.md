---
UID: NS:iddcx.IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
title: IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: Gives information about the OPM certificate size.
old-location: display\idarg_out_opm_get_certificate_size.htm
old-project: display
ms.assetid: 983e4bda-160d-4a3d-9a50-0ceabc70114f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDARG_OUT_OPM_GET_CERTIFICATE_SIZE, IDARG_OUT_OPM_GET_CERTIFICATE_SIZE structure [Display Devices], display.idarg_out_opm_get_certificate_size, iddcx/IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_OPM_GET_CERTIFICATE_SIZE structure


## -description



                 Gives information about the OPM certificate size.


## -syntax


````
typedef struct IDARG_OUT_OPM_GET_CERTIFICATE_SIZE {
  UINT CertificateSize;
} IDARG_OUT_OPM_GET_CERTIFICATE_SIZE, *IDARG_OUT_OPM_GET_CERTIFICATE_SIZE;
````


## -struct-fields




### -field CertificateSize


                     [out] Size of the OPM certificate.
                 

