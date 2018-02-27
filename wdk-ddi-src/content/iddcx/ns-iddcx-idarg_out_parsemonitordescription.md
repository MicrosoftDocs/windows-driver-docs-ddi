---
UID: NS:iddcx.IDARG_OUT_PARSEMONITORDESCRIPTION
title: IDARG_OUT_PARSEMONITORDESCRIPTION
author: windows-driver-content
description: Gives information about the number of monitor modes and preferred monitor mode of a monitor.
old-location: display\idarg_out_parsemonitordescription.htm
old-project: display
ms.assetid: 30f4c178-5ef8-4650-b396-1e4bc9cc9125
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IDARG_OUT_PARSEMONITORDESCRIPTION, IDARG_OUT_PARSEMONITORDESCRIPTION structure [Display Devices], display.idarg_out_parsemonitordescription, iddcx/IDARG_OUT_PARSEMONITORDESCRIPTION
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
-	IDARG_OUT_PARSEMONITORDESCRIPTION
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_PARSEMONITORDESCRIPTION structure


## -description



                 Gives information about the number of monitor modes and  preferred monitor mode of a monitor.


## -syntax


````
typedef struct IDARG_OUT_PARSEMONITORDESCRIPTION {
  UINT MonitorModeBufferOutputCount;
  UINT PreferredMonitorModeIdx;
} IDARG_OUT_PARSEMONITORDESCRIPTION, *IDARG_OUT_PARSEMONITORDESCRIPTION;
````


## -struct-fields




### -field MonitorModeBufferOutputCount


                     [out] If the <a href="..\iddcx\ns-iddcx-idarg_in_parsemonitordescription.md">IDARG_IN_PARSEMONITORDESCRIPTION</a> value <b>pMonitorModes</b> was NULL, then the driver should set this to the number of monitor modes the driver would generate for the specified monitor description. f the <b>IDARG_IN_PARSEMONITORDESCRIPTION</b> value <b>pMonitorModes</b> was non-NULL then this is the count of the monitor modes that the driver copied to that buffer.


### -field PreferredMonitorModeIdx


                     [out] Index into the <b>pMonitorModes</b> array of the preferred mode monitor mode, a value of <b>NO_PREFERRED_MODE</b>indicates that there is no preferred monitor mode.

