---
UID: NS:iddcx.IDDCX_OPM_CONFIGURE_PARAMETERS
title: IDDCX_OPM_CONFIGURE_PARAMETERS
author: windows-driver-content
description: Gives information about the OPM configure parameters.
old-location: display\iddcx_opm_configure_parameters.htm
old-project: display
ms.assetid: 88d8171f-8ed4-40af-8c05-7421895dca26
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: iddcx/IDDCX_OPM_CONFIGURE_PARAMETERS, display.iddcx_opm_configure_parameters, IDDCX_OPM_CONFIGURE_PARAMETERS structure [Display Devices], IDDCX_OPM_CONFIGURE_PARAMETERS
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
-	IDDCX_OPM_CONFIGURE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_OPM_CONFIGURE_PARAMETERS structure


## -description


Gives information about the OPM configure parameters.


## -syntax


````
typedef struct IDDCX_OPM_CONFIGURE_PARAMETERS {
  UINT                     Size;
  OPM_CONFIGURE_PARAMETERS ConfigParameters;
} IDDCX_OPM_CONFIGURE_PARAMETERS, *IDDCX_OPM_CONFIGURE_PARAMETERS;
````


## -struct-fields




### -field Size


                     Total size of the structure.
                 


### -field ConfigParameters


                     Configuration parameters.
                 

