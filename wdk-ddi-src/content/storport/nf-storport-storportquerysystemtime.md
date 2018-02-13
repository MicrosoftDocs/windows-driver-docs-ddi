---
UID: NF:storport.StorPortQuerySystemTime
title: StorPortQuerySystemTime function
author: windows-driver-content
description: The StoriPortQuerySystemTime routine obtains the current system time.
old-location: storage\storportquerysystemtime.htm
old-project: storage
ms.assetid: 20677d16-136c-47d7-a19b-21731433298e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortQuerySystemTime routine [Storage Devices], StorPortQuerySystemTime, storport/StorPortQuerySystemTime, storprt_fcad0e23-f796-4cd9-935c-6db56a63d899.xml, storage.storportquerysystemtime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
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
req.lib: Storport.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortQuerySystemTime
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortQuerySystemTime function


## -description


The <b>StoriPortQuerySystemTime</b> routine obtains the current system time.


## -syntax


````
STORPORT_API VOID StorPortQuerySystemTime(
  _Out_ PLARGE_INTEGER CurrentTime
);
````


## -parameters




### -param CurrentTime [out]

Pointer to the current time, on return. 


## -returns



None 




## -remarks



The system time returned in <i>CurrentTime</i> is the number of 100-nanosecond intervals that have elapsed since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. 




## -see-also

<a href="..\srb\nf-srb-scsiportquerysystemtime.md">ScsiPortQuerySystemTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortQuerySystemTime routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

