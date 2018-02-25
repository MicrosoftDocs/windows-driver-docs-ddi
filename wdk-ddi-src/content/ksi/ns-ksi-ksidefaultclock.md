---
UID: NS:ksi.KSIDEFAULTCLOCK
title: KSIDEFAULTCLOCK
author: windows-driver-content
description: "."
old-location: stream\ksidefaultclock.htm
old-project: stream
ms.assetid: 08509C28-DDD4-4060-A16A-857A6BF6F6E1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSIDEFAULTCLOCK, ,, A, C, D, E, F, I, K, KSIDEFAULTCLOCK, KSIDEFAULTCLOCK structure [Streaming Media Devices], L, O, P, PKSIDEFAULTCLOCK, PKSIDEFAULTCLOCK structure pointer [Streaming Media Devices], S, T, U, ksi/KSIDEFAULTCLOCK, ksi/PKSIDEFAULTCLOCK, stream.ksidefaultclock"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksi.h
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
-	Ksi.h
apiname:
-	KSIDEFAULTCLOCK
product: Windows
targetos: Windows
req.typenames: KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
---

# KSIDEFAULTCLOCK structure


## -description





## -syntax


````
typedef struct {
  LONGLONG                  Frequency;
  LONGLONG                  LastDueTime;
  LONGLONG                  RunningTimeDelta;
  LONGLONG                  LastRunningTime;
  KSPIN_LOCK                TimeAccessLock;
  LIST_ENTRY                EventQueue;
  KSPIN_LOCK                EventQueueLock;
  KTIMER                    QueueTimer;
  KDPC                      QueueDpc;
  LONG                      ReferenceCount;
  KSSTATE                   State;
  LONGLONG                  SuspendDelta;
  LONGLONG                  SuspendTime;
  PFNKSSETTIMER             SetTimer;
  PFNKSCANCELTIMER          CancelTimer;
  PFNKSCLOCK_CORRELATEDTIME CorrelatedTime;
  PVOID                     Context;
  KSRESOLUTION              Resolution;
  KEVENT                    FreeEvent;
  LONG                      ExternalTimeReferenceCount;
  BOOLEAN                   ExternalTimeValid;
  LONGLONG                  LastStreamTime;
} KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK;
````


## -struct-fields




### -field Frequency


### -field LastDueTime


### -field RunningTimeDelta


### -field LastRunningTime


### -field TimeAccessLock


### -field EventQueue


### -field EventQueueLock


### -field QueueTimer


### -field QueueDpc


### -field ReferenceCount


### -field State


### -field SuspendDelta


### -field SuspendTime


### -field SetTimer


### -field CancelTimer


### -field CorrelatedTime


### -field Context


### -field Resolution


### -field FreeEvent


### -field ExternalTimeReferenceCount


### -field ExternalTimeValid


### -field LastStreamTime

