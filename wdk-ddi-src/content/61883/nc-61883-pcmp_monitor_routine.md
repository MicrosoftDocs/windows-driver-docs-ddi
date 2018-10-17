---
UID: NC:61883.PCMP_MONITOR_ROUTINE
title: PCMP_MONITOR_ROUTINE
author: windows-driver-content
description: This routine is called for plug monitoring.
old-location: ieee\pcmp_monitor_routine.htm
tech.root: IEEE
ms.assetid: E140D097-EE2F-4179-A43D-570397459762
ms.date: 2/15/2018
ms.keywords: 61883/CmpMonitorRoutine, CmpMonitorRoutine, CmpMonitorRoutine callback function [Buses], IEEE.pcmp_monitor_routine, PCMP_MONITOR_ROUTINE, PCMP_MONITOR_ROUTINE callback
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	61883.h
api_name:
-	CmpMonitorRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCMP_MONITOR_ROUTINE callback function


## -description


This routine is called for plug monitoring.


## -parameters




### -param MonitorInfo [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537050">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified. 


## -returns



This callback does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

