---
UID: NC:61883.PCMP_NOTIFY_ROUTINE
title: PCMP_NOTIFY_ROUTINE
author: windows-driver-content
description: This routine is called for plug notification.
old-location: ieee\pcmp_notify_routine.htm
old-project: IEEE
ms.assetid: 0576D73A-0A36-4AB7-952C-19B56FD246D8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IEEE.pcmp_notify_routine, CmpNotifyRoutine callback function, CmpNotifyRoutine, PCMP_NOTIFY_ROUTINE, PCMP_NOTIFY_ROUTINE, 61883/CmpNotifyRoutine, CmpNotifyRoutine callback function, CmpNotifyRoutine
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
-	CmpNotifyRoutine
product: Windows
targetos: Windows
req.typenames: TOPOLOGY_MAP, *PTOPOLOGY_MAP
---

# PCMP_NOTIFY_ROUTINE callback


## -description


This routine is called for plug notification.


## -prototype


````
PCMP_NOTIFY_ROUTINE CmpNotifyRoutine;

void CmpNotifyRoutine(
  _In_ PCMP_NOTIFY_INFO NotifyInfo
)
{ ... }

typedef PCMP_NOTIFY_ROUTINE CmpNotifyRoutine;
````


## -parameters




#### - NotifyInfo [in]

Specifies the notification information.


## -returns


This callback does not return a value.


