---
UID: NS:iddcx.IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
title: IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
author: windows-driver-content
description: Gives information about the buffer that the driver will copy configuration parameters to.
old-location: display\idarg_in_opm_configure_protected_output.htm
tech.root: display
ms.assetid: 523b904c-c833-40f2-8173-7ec1c6687b26
ms.date: 5/10/2018
ms.keywords: IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT, IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT structure [Display Devices], display.idarg_in_opm_configure_protected_output, iddcx/IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
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
-	IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT structure


## -description



                 Gives information about the buffer that the driver will copy configuration parameters to.
             


## -struct-fields




### -field ConfigParameters


                     [in] Configuration parameters
                 


### -field AdditionalParametersSizeInBytes


                     [in] Size of additional parameter buffer
                 


### -field pAdditionalParameters


                     [in] A pointer to a buffer that the driver copies the configuration info to.
                 

