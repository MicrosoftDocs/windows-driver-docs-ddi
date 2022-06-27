---
UID: NE:storport._STOR_SPINLOCK
title: STOR_SPINLOCK (storport.h)
description: The STOR_SPINLOCK enumeration is used to specify the type of a spinlock.
old-location: storage\stor_spinlock.htm
tech.root: storage
ms.date: 05/24/2022
keywords: ["STOR_SPINLOCK enumeration"]
ms.keywords: DpcLock, InterruptLock, STOR_SPINLOCK, STOR_SPINLOCK enumeration [Storage Devices], StartIoLock, _STOR_SPINLOCK, storage.stor_spinlock, storport/DpcLock, storport/InterruptLock, storport/STOR_SPINLOCK, storport/StartIoLock, structs-general_53d45f74-68b2-4839-81c1-c93a2773f0d8.xml
req.header: storport.h
req.include-header: Storport.h
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
req.typenames: STOR_SPINLOCK
f1_keywords:
 - _STOR_SPINLOCK
 - storport/_STOR_SPINLOCK
 - STOR_SPINLOCK
 - storport/STOR_SPINLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_SPINLOCK
 - STOR_SPINLOCK
---

# STOR_SPINLOCK enumeration

## -description

The **STOR_SPINLOCK** enumeration is used to specify the type of a spinlock.

## -enum-fields

### -field DpcLock

Indicates a DPC spinlock.

### -field StartIoLock

Indicates a StartIo spinlock.

### -field InterruptLock

Indicates an Interrupt spinlock.

### -field ThreadedDpcLock

Indicates a threaded DPC spinlock.

### -field DpcLevelLock

Indicates a spinlock that is to be used when the IRQL level is already at DPC level.

## -see-also

[**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md)
