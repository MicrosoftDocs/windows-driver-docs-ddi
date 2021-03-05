---
UID: NE:storport._STOR_THREAD_PRIORITY
tech.root: storage
title: STOR_THREAD_PRIORITY
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: **STOR_THREAD_PRIORITY** specifies the priority for a StorPort miniport-created thread.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_THREAD_PRIORITY
 - PSTOR_THREAD_PRIORITY
 - STOR_THREAD_PRIORITY
f1_keywords:
 - _STOR_THREAD_PRIORITY
 - storport/_STOR_THREAD_PRIORITY
 - PSTOR_THREAD_PRIORITY
 - storport/PSTOR_THREAD_PRIORITY
 - STOR_THREAD_PRIORITY
 - storport/STOR_THREAD_PRIORITY
dev_langs:
 - c++
---

## -description

**STOR_THREAD_PRIORITY** specifies the priority for a StorPort miniport-created thread.

## -enum-fields

### -field StorThreadPriorityBackground

System priority level. The assigned priority level is 7.

### -field StorThreadPriorityNormal

System priority level. The assigned priority level is 8.

### -field StorThreadPriorityDelayed

Indicates an ordinary worker thread. The assigned priority level is 12.

### -field StorThreadPriorityCritical

Indicates a real-time system worker thread. The assigned priority level is 13.

### -field StorThreadPrioritySuperCritical

System priority level. The assigned priority level is 14.

### -field StorThreadPriorityHyperCritical

System priority level. The assigned priority level is 15.

### -field StorThreadPriorityRealTime

System priority level. The assigned priority level is 18.

## -remarks

A miniport sets thread priority when it calls [**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md) to create a thread, and can change thread priority in [**StorPortSetPriorityThread**](nf-storport-storportsetsystemthread.md).

Every thread has a scheduling priority (its thread priority). Higher values indicate higher priority threads.

See [Thread Priorities](/windows-hardware/drivers/kernel/thread-priorities) for general information.

## -see-also

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)

[**StorPortSetPriorityThread**](nf-storport-storportsetsystemthread.md)
