---
UID: NS:iscsiop._RemoveConnectionFromSession_OUT
title: _RemoveConnectionFromSession_OUT (iscsiop.h)
description: The RemoveConnectionFromSession_OUT structure holds the output data for the RemoveConnectionFromSession method, which is used to remove a connection from a session.
old-location: storage\removeconnectionfromsession_out.htm
tech.root: storage
ms.assetid: 00c6c94e-06a8-40ec-8ddd-4a4191fa1ec6
ms.date: 03/29/2018
keywords: ["_RemoveConnectionFromSession_OUT structure"]
ms.keywords: "*PRemoveConnectionFromSession_OUT, PRemoveConnectionFromSession_OUT, PRemoveConnectionFromSession_OUT structure pointer [Storage Devices], RemoveConnectionFromSession_OUT, RemoveConnectionFromSession_OUT structure [Storage Devices], _RemoveConnectionFromSession_OUT, iscsiop/PRemoveConnectionFromSession_OUT, iscsiop/RemoveConnectionFromSession_OUT, storage.removeconnectionfromsession_out, structs-iSCSI_a986a037-b861-4c2b-8402-86dbf7c09942.xml"
f1_keywords:
 - "iscsiop/RemoveConnectionFromSession_OUT"
 - "RemoveConnectionFromSession_OUT"
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
- RemoveConnectionFromSession_OUT
targetos: Windows
req.typenames: RemoveConnectionFromSession_OUT, *PRemoveConnectionFromSession_OUT
---

# _RemoveConnectionFromSession_OUT structure


## -description


The RemoveConnectionFromSession_OUT structure holds the output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removeconnectionfromsession">RemoveConnectionFromSession</a> method, which is used to remove a connection from a session.


## -struct-fields




### -field Status

This specifies the status of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removeconnectionfromsession">RemoveConnectionFromSession</a> operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removeconnectionfromsession">RemoveConnectionFromSession</a>
 

 

