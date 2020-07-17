---
UID: NS:iddcx.IDARG_IN_ADAPTER_INIT
title: IDARG_IN_ADAPTER_INIT (iddcx.h)
description: Initializes an adapter that will be hosted on a WDF device.
old-location: display\idarg_in_adapter_init.htm
tech.root: display
ms.assetid: 2db324c8-69b1-4497-b6a7-76047baeca19
ms.date: 05/10/2018
keywords: ["IDARG_IN_ADAPTER_INIT structure"]
ms.keywords: IDARG_IN_ADAPTER_INIT, IDARG_IN_ADAPTER_INIT structure [Display Devices], display.idarg_in_adapter_init, iddcx/IDARG_IN_ADAPTER_INIT
f1_keywords:
 - "iddcx/IDARG_IN_ADAPTER_INIT"
 - "IDARG_IN_ADAPTER_INIT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iddcx.h
api_name:
- IDARG_IN_ADAPTER_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_ADAPTER_INIT structure


## -description



                 Initializes an adapter that will be hosted on a WDF device.
             


## -struct-fields




### -field WdfDevice


                     The WDF device that will be hosting this WDDM adapter object.
                 


### -field pCaps


                     [in] A reference  to the capabilities of the adapter.
                 


### -field ObjectAttributes


                     [in][optional] Object attributes that are used to initialize the WDF adapter object.
                 

