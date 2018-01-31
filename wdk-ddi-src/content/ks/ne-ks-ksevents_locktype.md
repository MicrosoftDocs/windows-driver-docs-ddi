---
UID: NE:ks.KSEVENTS_LOCKTYPE
title: KSEVENTS_LOCKTYPE
author: windows-driver-content
description: The KSEVENTS_LOCKTYPE enumeration identifies the type of exclusion lock. The types are used with EventFlags in several event-set helper functions.
old-location: stream\ksevents_locktype.htm
old-project: stream
ms.assetid: 775d08ad-40c2-44b7-af02-6c182301e46f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSEVENTS_FMUTEX, ks/KSEVENTS_ERESOURCE, KSEVENTS_FMUTEXUNSAFE, ks/KSEVENTS_FMUTEXUNSAFE, ks/KSEVENTS_SPINLOCK, KSEVENTS_ERESOURCE, KSEVENTS_NONE, ks/KSEVENTS_LOCKTYPE, KSEVENTS_MUTEX, KSEVENTS_LOCKTYPE enumeration [Streaming Media Devices], ks/KSEVENTS_NONE, stream.ksevents_locktype, KSEVENTS_SPINLOCK, ks/KSEVENTS_FMUTEX, ks/KSEVENTS_INTERRUPT, ks-struct_293dbf13-1dbe-478e-83fb-d38e17e4a697.xml, KSEVENTS_LOCKTYPE, ks/KSEVENTS_MUTEX, KSEVENTS_INTERRUPT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSEVENTS_LOCKTYPE
product: Windows
targetos: Windows
req.typenames: KSEVENTS_LOCKTYPE
---

# KSEVENTS_LOCKTYPE enumeration


## -description


The KSEVENTS_LOCKTYPE enumeration identifies the type of exclusion lock. The types are used with <i>EventFlags</i> in several event-set helper functions.


## -syntax


````
typedef enum  { 
  KSEVENTS_NONE          = 0,
  KSEVENTS_SPINLOCK      = 1,
  KSEVENTS_MUTEX         = 2,
  KSEVENTS_FMUTEX        = 3,
  KSEVENTS_FMUTEXUNSAFE  = 4,
  KSEVENTS_INTERRUPT     = 5,
  KSEVENTS_ERESOURCE     = 6
} KSEVENTS_LOCKTYPE;
````


## -enum-fields




#### - KSEVENTS_NONE

No lock.


#### - KSEVENTS_SPINLOCK

Lock is assumed to be a KSPIN_LOCK.


#### - KSEVENTS_MUTEX

Lock is assumed to be a KMUTEX.


#### - KSEVENTS_FMUTEX

Lock is assumed to be a FAST_MUTEX and is acquired by raising IRQL to APC_LEVEL.


#### - KSEVENTS_FMUTEXUNSAFE

Lock is assumed to be a FAST_MUTEX and is acquired without raising IRQL to APC_LEVEL.


#### - KSEVENTS_INTERRUPT

Lock is assumed to be an interrupt synchronization spin lock.


#### - KSEVENTS_ERESOURCE

Lock is assumed to be an ERESOURCE.

