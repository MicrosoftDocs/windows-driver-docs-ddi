---
UID: NS:1394._IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
title: _IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME (1394.h)
description: This structure contains the fields necessary for the Bus driver to carry out an IsochQueryCurrentCycleTime request.
old-location: ieee\irb_req_isoch_query_current_cycle_time.htm
tech.root: IEEE
ms.assetid: 4C42FB6D-BD5B-4376-A618-15AD6754AD9B
ms.date: 02/15/2018
keywords: ["IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME structure"]
ms.keywords: 1394/IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME, IEEE.irb_req_isoch_query_current_cycle_time, IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME, IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME structure [Buses], _IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
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
targetos: Windows
req.typenames: IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
f1_keywords:
 - _IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
 - 1394/_IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
 - IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
 - 1394/IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME
---

# _IRB_REQ_ISOCH_QUERY_CURRENT_CYCLE_TIME structure


## -description

 This structure contains the fields necessary for the Bus driver to carry out an
<b>IsochQueryCurrentCycleTime</b> request.

## -struct-fields

### -field CycleTime

On success, specifies the current isochronous cycle time. See the <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_cycle_time">CYCLE_TIME</a> entry for details.