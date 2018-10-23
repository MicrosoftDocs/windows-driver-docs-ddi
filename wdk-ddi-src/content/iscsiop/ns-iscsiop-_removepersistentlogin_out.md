---
UID: NS:iscsiop._RemovePersistentLogin_OUT
title: "_RemovePersistentLogin_OUT"
author: windows-driver-content
description: The RemovePersistentLogin_OUT structure holds the output data for the RemovePersistentLogin method.
old-location: storage\removepersistentlogin_out.htm
tech.root: storage
ms.assetid: 2b5aee65-ccf6-42c6-9bb3-dff93cb53cf0
ms.date: 03/29/2018
ms.keywords: "*PRemovePersistentLogin_OUT, PRemovePersistentLogin_OUT, PRemovePersistentLogin_OUT structure pointer [Storage Devices], RemovePersistentLogin_OUT, RemovePersistentLogin_OUT structure [Storage Devices], _RemovePersistentLogin_OUT, iscsiop/PRemovePersistentLogin_OUT, iscsiop/RemovePersistentLogin_OUT, storage.removepersistentlogin_out, structs-iSCSI_59f0b686-33c3-47be-9bd7-89d14f3ffc7b.xml"
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
-	RemovePersistentLogin_OUT
product:
- Windows
targetos: Windows
req.typenames: RemovePersistentLogin_OUT, *PRemovePersistentLogin_OUT
---

# _RemovePersistentLogin_OUT structure


## -description


The RemovePersistentLogin_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563995">RemovePersistentLogin</a> method.


## -struct-fields




### -field Status

On output from <b>RemovePersistentLogin</b>, the status of the operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563995">RemovePersistentLogin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564003">RemovePersistentLogin_IN</a>
 

 

