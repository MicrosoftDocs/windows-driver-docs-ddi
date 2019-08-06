---
UID: NF:ks.KsAcquireDeviceSecurityLock
title: KsAcquireDeviceSecurityLock function (ks.h)
description: The KsAcquireDeviceSecurityLock function acquires the security lock associated with a device object.
old-location: stream\ksacquiredevicesecuritylock.htm
tech.root: stream
ms.assetid: a5a003c1-fa35-461d-8a47-a1a7bc2375b4
ms.date: 04/23/2018
ms.keywords: KsAcquireDeviceSecurityLock, KsAcquireDeviceSecurityLock function [Streaming Media Devices], ks/KsAcquireDeviceSecurityLock, ksfunc_dd097c63-acd6-4de2-b3c9-a50e55e3f3f1.xml, stream.ksacquiredevicesecuritylock
ms.topic: function
f1_keywords:
 - "ks/KsAcquireDeviceSecurityLock"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAcquireDeviceSecurityLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAcquireDeviceSecurityLock function


## -description


The <b>KsAcquireDeviceSecurityLock</b> function acquires the security lock associated with a device object. An exclusive lock is acquired when changing a security descriptor. When manipulating the security of any object under a particular device object, this lock must be acquired.


## -parameters




### -param Header [in]

Points to a driver-allocated device header, previously allocated by <b>KsAllocateDeviceHeader,</b> for the device object described by the KSDEVICE_HEADER structure.


### -param Exclusive [in]

Indicates, if set to <b>TRUE</b>, that the lock is to be acquired exclusively.


## -returns



None




## -remarks



A shared lock is acquired when validating access during a create. An exclusive lock is acquired when changing a security descriptor. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksallocatedeviceheader">KsAllocateDeviceHeader</a>
 

 

