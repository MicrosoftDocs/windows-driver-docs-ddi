---
UID: NS:iscsiop._ScsiReportLuns_IN
title: "_ScsiReportLuns_IN"
author: windows-driver-content
description: The ScsiReportLuns_IN structure holds the input data for the ScsiReportLuns method.
old-location: storage\scsireportluns_in.htm
old-project: storage
ms.assetid: ba1d67f7-cb90-473a-849d-7990889e4a40
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PScsiReportLuns_IN, ScsiReportLuns_IN, storage.scsireportluns_in, _ScsiReportLuns_IN, iscsiop/PScsiReportLuns_IN, *PScsiReportLuns_IN, iscsiop/ScsiReportLuns_IN, PScsiReportLuns_IN structure pointer [Storage Devices], structs-iSCSI_1bc2b9de-bb9a-417a-bbe3-07167f866b7b.xml, ScsiReportLuns_IN structure [Storage Devices]
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
-	ScsiReportLuns_IN
product: Windows
targetos: Windows
req.typenames: "*PScsiReportLuns_IN, ScsiReportLuns_IN"
---

# _ScsiReportLuns_IN structure


## -description


The ScsiReportLuns_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a> method.


## -syntax


````
typedef struct _ScsiReportLuns_IN {
  ULONGLONG UniqueSessionId;
} ScsiReportLuns_IN, *PScsiReportLuns_IN;
````


## -struct-fields




#### - UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. 


## -remarks


You must implement this method.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="..\hbapiwmi\ns-hbapiwmi-_scsireportluns_out.md">ScsiReportLuns_OUT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReportLuns_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

