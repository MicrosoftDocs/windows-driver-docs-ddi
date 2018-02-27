---
UID: NS:iddcx.IDARG_OUT_OPM_GET_INFOMATION
title: IDARG_OUT_OPM_GET_INFOMATION
author: windows-driver-content
description: Gives the OPM information that was requested.
old-location: display\idarg_out_opm_get_infomation.htm
old-project: display
ms.assetid: 7c51b228-480d-4e19-aa70-4fcc44ffae16
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IDARG_OUT_OPM_GET_INFOMATION, IDARG_OUT_OPM_GET_INFOMATION structure [Display Devices], display.idarg_out_opm_get_infomation, iddcx/IDARG_OUT_OPM_GET_INFOMATION
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
-	IDARG_OUT_OPM_GET_INFOMATION
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_OPM_GET_INFOMATION structure


## -description



                 Gives the OPM information that was requested.
             


## -syntax


````
typedef struct IDARG_OUT_OPM_GET_INFOMATION {
  IDDCX_OPM_REQUESTED_INFORMATION RequestedInformation;
} IDARG_OUT_OPM_GET_INFOMATION, *IDARG_OUT_OPM_GET_INFOMATION;
````


## -struct-fields




### -field RequestedInformation


                      [out] The OPM information that was requested.
                 

