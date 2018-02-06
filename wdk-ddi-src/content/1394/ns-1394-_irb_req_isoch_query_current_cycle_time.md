---
UID: NS:1394._IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
title: "_IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME"
author: windows-driver-content
description: This structure contains the fields necessary for the Bus driver to carry out an IsochQueryCurrentCycleTime request.
old-location: ieee\irb_req_isoch_query_current_cycle_time.htm
old-project: IEEE
ms.assetid: 4C42FB6D-BD5B-4376-A618-15AD6754AD9B
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "_IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME, IEEE.irb_req_isoch_query_current_cycle_time, IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME structure [Buses], 1394/IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME, IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
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
-	1394.h
apiname:
-	IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
---

# _IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME structure


## -description


 This structure contains the fields necessary for the Bus driver to carry out an
<b>IsochQueryCurrentCycleTime</b> request.


## -syntax


````
typedef struct _IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME {
  CYCLE_TIME CycleTime;
} IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME;
````


## -struct-fields




### -field CycleTime

On success, specifies the current isochronous cycle time. See the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537067">CYCLE_TIME</a> entry for details.

