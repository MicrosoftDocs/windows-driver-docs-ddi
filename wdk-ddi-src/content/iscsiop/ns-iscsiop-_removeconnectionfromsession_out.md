---
UID: NS:iscsiop._RemoveConnectionFromSession_OUT
title: "_RemoveConnectionFromSession_OUT"
author: windows-driver-content
description: The RemoveConnectionFromSession_OUT structure holds the output data for the RemoveConnectionFromSession method, which is used to remove a connection from a session.
old-location: storage\removeconnectionfromsession_out.htm
old-project: storage
ms.assetid: 00c6c94e-06a8-40ec-8ddd-4a4191fa1ec6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PRemoveConnectionFromSession_OUT, PRemoveConnectionFromSession_OUT, PRemoveConnectionFromSession_OUT structure pointer [Storage Devices], RemoveConnectionFromSession_OUT, RemoveConnectionFromSession_OUT structure [Storage Devices], _RemoveConnectionFromSession_OUT, iscsiop/PRemoveConnectionFromSession_OUT, iscsiop/RemoveConnectionFromSession_OUT, storage.removeconnectionfromsession_out, structs-iSCSI_a986a037-b861-4c2b-8402-86dbf7c09942.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	RemoveConnectionFromSession_OUT
product: Windows
targetos: Windows
req.typenames: RemoveConnectionFromSession_OUT, *PRemoveConnectionFromSession_OUT
---

# _RemoveConnectionFromSession_OUT structure


## -description


The RemoveConnectionFromSession_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a> method, which is used to remove a connection from a session.


## -struct-fields




### -field Status

This specifies the status of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563973">RemoveConnectionFromSession</a>
 

 

