---
UID: NS:iscsiop._RemoveConnectionFromSession_IN
title: "_RemoveConnectionFromSession_IN"
author: windows-driver-content
description: The RemoveConnectionFromSession_IN structure holds the input data for the RemoveConnectionFromSession method, which is used to remove a connection from a session.
old-location: storage\removeconnectionfromsession_in.htm
old-project: storage
ms.assetid: dd5fd1f2-7040-40ee-bf9c-42e77c9738da
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: RemoveConnectionFromSession_IN, iscsiop/RemoveConnectionFromSession_IN, RemoveConnectionFromSession_IN structure [Storage Devices], PRemoveConnectionFromSession_IN structure pointer [Storage Devices], _RemoveConnectionFromSession_IN, iscsiop/PRemoveConnectionFromSession_IN, *PRemoveConnectionFromSession_IN, storage.removeconnectionfromsession_in, PRemoveConnectionFromSession_IN, structs-iSCSI_7dca8bd4-ebf8-4ccc-996a-852fabba5df3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
apiname:
-	RemoveConnectionFromSession_IN
product: Windows
targetos: Windows
req.typenames: RemoveConnectionFromSession_IN, *PRemoveConnectionFromSession_IN
---

# _RemoveConnectionFromSession_IN structure


## -description


The RemoveConnectionFromSession_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a> method, which is used to remove a connection from a session.


## -syntax


````
typedef struct _RemoveConnectionFromSession_IN {
  ULONGLONG UniqueSessionId;
  ULONGLONG UniqueConnectionId;
} RemoveConnectionFromSession_IN, *PRemoveConnectionFromSession_IN;
````


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field UniqueConnectionId

A 64-bit integer that uniquely identifies the connection. Do not confuse this value with the connection ID (CID).


## -remarks


You must implement this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveConnectionFromSession_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

