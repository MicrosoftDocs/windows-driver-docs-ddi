---
UID: NS:iscsiop._ScsiReportLuns_IN
title: _ScsiReportLuns_IN (iscsiop.h)
description: The ScsiReportLuns_IN structure holds the input data for the ScsiReportLuns method.
old-location: storage\scsireportluns_in.htm
tech.root: storage
ms.assetid: ba1d67f7-cb90-473a-849d-7990889e4a40
ms.date: 03/29/2018
keywords: ["ScsiReportLuns_IN structure"]
ms.keywords: "*PScsiReportLuns_IN, PScsiReportLuns_IN, PScsiReportLuns_IN structure pointer [Storage Devices], ScsiReportLuns_IN, ScsiReportLuns_IN structure [Storage Devices], _ScsiReportLuns_IN, iscsiop/PScsiReportLuns_IN, iscsiop/ScsiReportLuns_IN, storage.scsireportluns_in, structs-iSCSI_1bc2b9de-bb9a-417a-bbe3-07167f866b7b.xml"
f1_keywords:
 - "iscsiop/ScsiReportLuns_IN"
 - "ScsiReportLuns_IN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- ScsiReportLuns_IN
targetos: Windows
req.typenames: ScsiReportLuns_IN, *PScsiReportLuns_IN
---

# _ScsiReportLuns_IN structure


## -description


The ScsiReportLuns_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireportluns6">ScsiReportLuns</a> method.


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. 


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireportluns6">ScsiReportLuns</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_scsireportluns_out">ScsiReportLuns_OUT</a>
 

 

