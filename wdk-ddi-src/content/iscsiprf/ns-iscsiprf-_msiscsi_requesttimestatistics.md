---
UID: NS:iscsiprf._MSiSCSI_RequestTimeStatistics
title: _MSiSCSI_RequestTimeStatistics (iscsiprf.h)
description: The MSiSCSI_RequestTimeStatistics structure is used by iSCSI initiators to report request time statistics.
old-location: storage\msiscsi_requesttimestatistics.htm
tech.root: storage
ms.assetid: fb884cff-dedb-44cf-b9ea-306bfa66b06f
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_RequestTimeStatistics, MSiSCSI_RequestTimeStatistics, MSiSCSI_RequestTimeStatistics structure [Storage Devices], PMSiSCSI_RequestTimeStatistics, PMSiSCSI_RequestTimeStatistics structure pointer [Storage Devices], _MSiSCSI_RequestTimeStatistics, iscsiprf/MSiSCSI_RequestTimeStatistics, iscsiprf/PMSiSCSI_RequestTimeStatistics, storage.msiscsi_requesttimestatistics, structs-iSCSI_32f6d3e4-d3d4-431d-aff0-f956aa2c1594.xml"
ms.topic: struct
f1_keywords:
 - "iscsiprf/MSiSCSI_RequestTimeStatistics"
req.header: iscsiprf.h
req.include-header: Iscsiprf.h
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
- iscsiprf.h
api_name:
- MSiSCSI_RequestTimeStatistics
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_RequestTimeStatistics, *PMSiSCSI_RequestTimeStatistics
---

# _MSiSCSI_RequestTimeStatistics structure


## -description


The MSiSCSI_RequestTimeStatistics structure is used by iSCSI initiators to report request time statistics.


## -struct-fields




### -field iSCSIName

The iSCSI target name.


### -field CID

The iSCSI connection identifier (ID) for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the connection. Do not use this ID. Application software should use the connection identifier that the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods return in the UniqueConnectionId parameter.


### -field USID

The iSCSI session ID for this connection instance. This ID is an internal value that the iSCSI protocol uses to identify the session. Do not use this ID. Application software should use the session identifier that the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods return in the UniqueSessionId parameter.


### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the UniqueAdapterId member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_msiscsi_hbainformation">MSiSCSI_HBAInformation</a> structure.


### -field MaximumProcessingTime

The maximum time taken to process a request over this connection.


### -field AverageProcessingTime

The average time taken to process a request over this connection.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsimgt/ns-iscsimgt-_msiscsi_hbainformation">MSiSCSI_HBAInformation</a>
 

 

