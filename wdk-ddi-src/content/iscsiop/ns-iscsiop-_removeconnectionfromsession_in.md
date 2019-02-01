---
UID: NS:iscsiop._RemoveConnectionFromSession_IN
title: _RemoveConnectionFromSession_IN (iscsiop.h)
description: The RemoveConnectionFromSession_IN structure holds the input data for the RemoveConnectionFromSession method, which is used to remove a connection from a session.
old-location: storage\removeconnectionfromsession_in.htm
tech.root: storage
ms.assetid: dd5fd1f2-7040-40ee-bf9c-42e77c9738da
ms.date: 03/29/2018
ms.keywords: "*PRemoveConnectionFromSession_IN, PRemoveConnectionFromSession_IN, PRemoveConnectionFromSession_IN structure pointer [Storage Devices], RemoveConnectionFromSession_IN, RemoveConnectionFromSession_IN structure [Storage Devices], _RemoveConnectionFromSession_IN, iscsiop/PRemoveConnectionFromSession_IN, iscsiop/RemoveConnectionFromSession_IN, storage.removeconnectionfromsession_in, structs-iSCSI_7dca8bd4-ebf8-4ccc-996a-852fabba5df3.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	RemoveConnectionFromSession_IN
product:
- Windows
targetos: Windows
req.typenames: RemoveConnectionFromSession_IN, *PRemoveConnectionFromSession_IN
---

# _RemoveConnectionFromSession_IN structure


## -description


The RemoveConnectionFromSession_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a> method, which is used to remove a connection from a session.


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field UniqueConnectionId

A 64-bit integer that uniquely identifies the connection. Do not confuse this value with the connection ID (CID).


## -remarks



You must implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a>
 

 

