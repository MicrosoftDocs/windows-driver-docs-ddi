---
UID: NS:iddcx.IDARG_OUT_ADAPTER_INIT
title: IDARG_OUT_ADAPTER_INIT (iddcx.h)
description: Gives information about the initialized adapter that can be used by the OS to call functions.
old-location: display\idarg_out_adapter_init.htm
tech.root: display
ms.assetid: 55e4c835-88c8-403f-883c-182915aa614d
ms.date: 05/10/2018
ms.keywords: IDARG_OUT_ADAPTER_INIT, IDARG_OUT_ADAPTER_INIT structure [Display Devices], display.idarg_out_adapter_init, iddcx/IDARG_OUT_ADAPTER_INIT
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
-	IDARG_OUT_ADAPTER_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_ADAPTER_INIT structure


## -description


Gives information about the initialized adapter that can be used by the OS to call functions.
                 
             


## -struct-fields




### -field AdapterObject


                     [out] Handle to the adapter that the driver can use to identify it when calling OS functions.
                 

