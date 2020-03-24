---
UID: NS:iscsiop._AddConnectionToSession_OUT
title: _AddConnectionToSession_OUT (iscsiop.h)
description: The AddConnectionToSession_OUT structure holds output data for the AddConnectionToSession method.
old-location: storage\addconnectiontosession_out.htm
tech.root: storage
ms.assetid: 9c7df21b-c7cd-4492-b457-6c2e82286961
ms.date: 03/29/2018
keywords: ["_AddConnectionToSession_OUT structure"]
ms.keywords: "*PAddConnectionToSession_OUT, AddConnectionToSession_OUT, AddConnectionToSession_OUT structure [Storage Devices], PAddConnectionToSession_OUT, PAddConnectionToSession_OUT structure pointer [Storage Devices], _AddConnectionToSession_OUT, iscsiop/AddConnectionToSession_OUT, iscsiop/PAddConnectionToSession_OUT, storage.addconnectiontosession_out, structs-iSCSI_d630117d-61cb-4c93-97c3-2a0c0b13b04c.xml"
f1_keywords:
 - "iscsiop/AddConnectionToSession_OUT"
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
- AddConnectionToSession_OUT
product:
- Windows
targetos: Windows
req.typenames: AddConnectionToSession_OUT, *PAddConnectionToSession_OUT
---

# _AddConnectionToSession_OUT structure


## -description


The AddConnectionToSession_OUT structure holds output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> method.


## -struct-fields




### -field Status

The status of the <b>AddConnectionToSession </b>operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.  


### -field UniqueConnectionId

A 64-bit integer that uniquely identifies the connection across the entire network.


## -remarks



The iSCSI service requires this method. It is optional that you implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_addconnectiontosession_in">AddConnectionToSession_IN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-operations-wmi-class">MSiSCSI_Operations WMI Class</a>
 

 

