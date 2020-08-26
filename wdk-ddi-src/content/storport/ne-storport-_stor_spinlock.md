---
UID: NE:storport._STOR_SPINLOCK
title: _STOR_SPINLOCK (storport.h)
description: The STOR_SPINLOCK enumeration is used to specify the type of a spinlock.
old-location: storage\stor_spinlock.htm
tech.root: storage
ms.assetid: 73e5e994-4133-4651-bb94-1d21386be1cd
ms.date: 03/29/2018
keywords: ["STOR_SPINLOCK enumeration"]
ms.keywords: DpcLock, InterruptLock, STOR_SPINLOCK, STOR_SPINLOCK enumeration [Storage Devices], StartIoLock, _STOR_SPINLOCK, storage.stor_spinlock, storport/DpcLock, storport/InterruptLock, storport/STOR_SPINLOCK, storport/StartIoLock, structs-general_53d45f74-68b2-4839-81c1-c93a2773f0d8.xml
f1_keywords:
 - "storport/STOR_SPINLOCK"
 - "STOR_SPINLOCK"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- STOR_SPINLOCK
targetos: Windows
req.typenames: STOR_SPINLOCK
---

# _STOR_SPINLOCK enumeration


## -description


The STOR_SPINLOCK enumeration is used to specify the type of a spinlock.


## -enum-fields




### -field DpcLock

Indicates a DPC spinlock. 


### -field StartIoLock

Indicates a StartIo spinlock.  


### -field InterruptLock

Indicates an Interrupt spinlock.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>
 

 

