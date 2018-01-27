---
UID: NF:ks.KsAcquireDeviceSecurityLock
title: KsAcquireDeviceSecurityLock function
author: windows-driver-content
description: The KsAcquireDeviceSecurityLock function acquires the security lock associated with a device object.
old-location: stream\ksacquiredevicesecuritylock.htm
old-project: stream
ms.assetid: a5a003c1-fa35-461d-8a47-a1a7bc2375b4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsAcquireDeviceSecurityLock, stream.ksacquiredevicesecuritylock, ksfunc_dd097c63-acd6-4de2-b3c9-a50e55e3f3f1.xml, KsAcquireDeviceSecurityLock function [Streaming Media Devices], ks/KsAcquireDeviceSecurityLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ks.lib
-	Ks.dll
apiname: 
-	KsAcquireDeviceSecurityLock
product: Windows
targetos: Windows
req.typenames: 
---

# KsAcquireDeviceSecurityLock function


## -description


The <b>KsAcquireDeviceSecurityLock</b> function acquires the security lock associated with a device object. An exclusive lock is acquired when changing a security descriptor. When manipulating the security of any object under a particular device object, this lock must be acquired.


## -syntax


````
VOID KsAcquireDeviceSecurityLock(
  _In_ KSDEVICE_HEADER Header,
  _In_ BOOLEAN         Exclusive
);
````


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

<a href="..\ks\nf-ks-ksallocatedeviceheader.md">KsAllocateDeviceHeader</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAcquireDeviceSecurityLock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

