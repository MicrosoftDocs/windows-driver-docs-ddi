---
UID: NS:iddcx.IDARG_IN_ADAPTER_INIT_FINISHED
title: IDARG_IN_ADAPTER_INIT_FINISHED
author: windows-driver-content
description: Gives the status of the adapter initialization.
old-location: display\idarg_in_adapter_init_finished.htm
old-project: display
ms.assetid: 7ff07613-7c40-4310-856a-a44dc97c7f20
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, D, E, F, G, H, I, IDARG_IN_ADAPTER_INIT_FINISHED, IDARG_IN_ADAPTER_INIT_FINISHED structure [Display Devices], N, P, R, S, T, _, display.idarg_in_adapter_init_finished, iddcx/IDARG_IN_ADAPTER_INIT_FINISHED"
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
-	IDARG_IN_ADAPTER_INIT_FINISHED
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_ADAPTER_INIT_FINISHED structure


## -description



                 Gives the status of the adapter initialization.


## -syntax


````
typedef struct IDARG_IN_ADAPTER_INIT_FINISHED {
  NTSTATUS AdapterInitStatus;
} IDARG_IN_ADAPTER_INIT_FINISHED, *IDARG_IN_ADAPTER_INIT_FINISHED;
````


## -struct-fields




### -field AdapterInitStatus


                     The initialization status of the adapter.
                 

