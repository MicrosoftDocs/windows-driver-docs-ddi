---
UID: NS:iddcx.IDARG_OUT_MONITORCREATE
title: IDARG_OUT_MONITORCREATE
author: windows-driver-content
description: Gives information about the newly created monitor object.
old-location: display\idarg_out_monitorcreate.htm
old-project: display
ms.assetid: 713cd675-56a8-42d8-ac75-4af227c55dec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDARG_OUT_MONITORCREATE, IDARG_OUT_MONITORCREATE structure [Display Devices], display.idarg_out_monitorcreate, iddcx/IDARG_OUT_MONITORCREATE
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
-	IDARG_OUT_MONITORCREATE
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_MONITORCREATE structure


## -description


Gives information about the newly created monitor object.


## -syntax


````
typedef struct IDARG_OUT_MONITORCREATE {
  IDDCX_MONITOR MonitorObject;
} IDARG_OUT_MONITORCREATE, *IDARG_OUT_MONITORCREATE;
````


## -struct-fields




### -field MonitorObject


                     [out] Handle the driver can use to identify this monitor when calling OS functions.
                 

