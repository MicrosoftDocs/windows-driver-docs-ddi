---
UID: NS:iddcx.IDARG_IN_MAXDISPLAYPIPELINERATE
title: IDARG_IN_MAXDISPLAYPIPELINERATE
author: windows-driver-content
description: Gives information about the maximum display pipeline rate.
old-location: display\idarg_in_maxdisplaypipelinerate.htm
old-project: display
ms.assetid: 035c3d04-56e8-48ec-91d4-6d6a1a5037c4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_MAXDISPLAYPIPELINERATE structure [Display Devices], iddcx/IDARG_IN_MAXDISPLAYPIPELINERATE, IDARG_IN_MAXDISPLAYPIPELINERATE, display.idarg_in_maxdisplaypipelinerate
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
-	IDARG_IN_MAXDISPLAYPIPELINERATE
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_MAXDISPLAYPIPELINERATE structure


## -description



                 Gives information about the maximum display pipeline rate.


## -syntax


````
typedef struct IDARG_IN_MAXDISPLAYPIPELINERATE {
  IDDCX_UPDATE_REASON Reason;
  UINT64              MaxDisplayPipelineRate;
} IDARG_IN_MAXDISPLAYPIPELINERATE, *IDARG_IN_MAXDISPLAYPIPELINERATE;
````


## -struct-fields




### -field Reason


                     Indicates the reason why the driver is updating the rate.


### -field MaxDisplayPipelineRate


                     Indicates the maximum display pipeline rate. This is the new value for <b>IDDCX_ADAPTER_CAPS.MaxDisplayPipelineRate</b>

