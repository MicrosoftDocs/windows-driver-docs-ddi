---
UID: NC:61883.PCMP_MONITOR_ROUTINE
title: PCMP_MONITOR_ROUTINE (61883.h)
description: This routine is called for plug monitoring.
old-location: ieee\pcmp_monitor_routine.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["PCMP_MONITOR_ROUTINE callback function"]
ms.keywords: 61883/CmpMonitorRoutine, CmpMonitorRoutine, CmpMonitorRoutine callback function [Buses], IEEE.pcmp_monitor_routine, PCMP_MONITOR_ROUTINE, PCMP_MONITOR_ROUTINE callback
req.header: 61883.h
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
req.typenames: 
f1_keywords:
 - PCMP_MONITOR_ROUTINE
 - 61883/PCMP_MONITOR_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 61883.h
api_name:
 - PCMP_MONITOR_ROUTINE
---

# PCMP_MONITOR_ROUTINE callback function


## -description

This routine is called for plug monitoring.

## -parameters

### -param MonitorInfo 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_monitor_info">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>

