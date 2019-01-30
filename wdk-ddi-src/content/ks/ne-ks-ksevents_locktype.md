---
UID: NE:ks.__unnamed_enum_32
title: KSEVENTS_LOCKTYPE (ks.h)
description: The KSEVENTS_LOCKTYPE enumeration identifies the type of exclusion lock. The types are used with EventFlags in several event-set helper functions.
old-location: stream\ksevents_locktype.htm
tech.root: stream
ms.assetid: 775d08ad-40c2-44b7-af02-6c182301e46f
ms.date: 04/23/2018
ms.keywords: KSEVENTS_ERESOURCE, KSEVENTS_FMUTEX, KSEVENTS_FMUTEXUNSAFE, KSEVENTS_INTERRUPT, KSEVENTS_LOCKTYPE, KSEVENTS_LOCKTYPE enumeration [Streaming Media Devices], KSEVENTS_MUTEX, KSEVENTS_NONE, KSEVENTS_SPINLOCK, ks-struct_293dbf13-1dbe-478e-83fb-d38e17e4a697.xml, ks/KSEVENTS_ERESOURCE, ks/KSEVENTS_FMUTEX, ks/KSEVENTS_FMUTEXUNSAFE, ks/KSEVENTS_INTERRUPT, ks/KSEVENTS_LOCKTYPE, ks/KSEVENTS_MUTEX, ks/KSEVENTS_NONE, ks/KSEVENTS_SPINLOCK, stream.ksevents_locktype
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSEVENTS_LOCKTYPE
product:
- Windows
targetos: Windows
req.typenames: KSEVENTS_LOCKTYPE
---

# KSEVENTS_LOCKTYPE enumeration


## -description


The KSEVENTS_LOCKTYPE enumeration identifies the type of exclusion lock. The types are used with <i>EventFlags</i> in several event-set helper functions.


## -enum-fields




### -field KSEVENTS_NONE

No lock.


### -field KSEVENTS_SPINLOCK

Lock is assumed to be a KSPIN_LOCK.


### -field KSEVENTS_MUTEX

Lock is assumed to be a KMUTEX.


### -field KSEVENTS_FMUTEX

Lock is assumed to be a FAST_MUTEX and is acquired by raising IRQL to APC_LEVEL.


### -field KSEVENTS_FMUTEXUNSAFE

Lock is assumed to be a FAST_MUTEX and is acquired without raising IRQL to APC_LEVEL.


### -field KSEVENTS_INTERRUPT

Lock is assumed to be an interrupt synchronization spin lock.


### -field KSEVENTS_ERESOURCE

Lock is assumed to be an ERESOURCE.

