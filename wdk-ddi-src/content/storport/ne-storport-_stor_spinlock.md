---
UID: NE:storport._STOR_SPINLOCK
title: "_STOR_SPINLOCK"
author: windows-driver-content
description: The STOR_SPINLOCK enumeration is used to specify the type of a spinlock.
old-location: storage\stor_spinlock.htm
old-project: storage
ms.assetid: 73e5e994-4133-4651-bb94-1d21386be1cd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: STOR_SPINLOCK, storport/STOR_SPINLOCK, structs-general_53d45f74-68b2-4839-81c1-c93a2773f0d8.xml, StartIoLock, InterruptLock, _STOR_SPINLOCK, STOR_SPINLOCK enumeration [Storage Devices], DpcLock, storage.stor_spinlock, storport/InterruptLock, storport/StartIoLock, storport/DpcLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	STOR_SPINLOCK
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# _STOR_SPINLOCK enumeration


## -description


The STOR_SPINLOCK enumeration is used to specify the type of a spinlock.


## -syntax


````
typedef enum _STOR_SPINLOCK { 
  DpcLock        = 1,
  StartIoLock    = 2,
  InterruptLock  = 3
} STOR_SPINLOCK;
````


## -enum-fields




### -field DpcLock

Indicates a DPC spinlock. 


### -field StartIoLock

Indicates a StartIo spinlock.  


### -field InterruptLock

Indicates an Interrupt spinlock.


## -see-also

<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_SPINLOCK enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

