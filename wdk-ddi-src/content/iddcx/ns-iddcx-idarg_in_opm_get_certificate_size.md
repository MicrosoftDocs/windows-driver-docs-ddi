---
UID: NS:iddcx.IDARG_IN_OPM_GET_CERTIFICATE_SIZE
title: IDARG_IN_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: Gives information about the OPM certificate size.
old-location: display\idarg_in_opm_get_certificate_size.htm
old-project: display
ms.assetid: 42b8bd6c-c5be-45d0-9537-13d687ca5a48
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_OPM_GET_CERTIFICATE_SIZE, IDARG_IN_OPM_GET_CERTIFICATE_SIZE structure [Display Devices], iddcx/IDARG_IN_OPM_GET_CERTIFICATE_SIZE, display.idarg_in_opm_get_certificate_size
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDARG_IN_OPM_GET_CERTIFICATE_SIZE
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_OPM_GET_CERTIFICATE_SIZE structure


## -description


Gives information about the OPM certificate size.


## -syntax


````
typedef struct IDARG_IN_OPM_GET_CERTIFICATE_SIZE {
  OPM_VIDEO_OUTPUT_SEMANTICS CertificateType;
} IDARG_IN_OPM_GET_CERTIFICATE_SIZE, *IDARG_IN_OPM_GET_CERTIFICATE_SIZE;
````


## -struct-fields




### -field CertificateType


                     [in] Type of certificate the size request is for.
                 

