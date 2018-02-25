---
UID: NC:61883.PCMP_MONITOR_ROUTINE
title: PCMP_MONITOR_ROUTINE
author: windows-driver-content
description: This routine is called for plug monitoring.
old-location: ieee\pcmp_monitor_routine.htm
old-project: IEEE
ms.assetid: E140D097-EE2F-4179-A43D-570397459762
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 61883/CmpMonitorRoutine, CmpMonitorRoutine, CmpMonitorRoutine callback function [Buses], IEEE.pcmp_monitor_routine, PCMP_MONITOR_ROUTINE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	61883.h
apiname:
-	CmpMonitorRoutine
product: Windows
targetos: Windows
req.typenames: TOPOLOGY_MAP, *PTOPOLOGY_MAP
---

# PCMP_MONITOR_ROUTINE callback


## -description


This routine is called for plug monitoring.


## -prototype


````
PCMP_MONITOR_ROUTINE CmpMonitorRoutine;

void CmpMonitorRoutine(
  _In_ PCMP_MONITOR_INFO MonitorInfo
)
{ ... }

typedef PCMP_MONITOR_ROUTINE CmpMonitorRoutine;
````


## -parameters




### -param MonitorInfo [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537050">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified. 


## -returns



This callback does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20PCMP_MONITOR_ROUTINE callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

