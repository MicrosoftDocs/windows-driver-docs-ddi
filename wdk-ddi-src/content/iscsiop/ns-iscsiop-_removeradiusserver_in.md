---
UID: NS:iscsiop._RemoveRADIUSServer_IN
title: "_RemoveRADIUSServer_IN" (iscsiop.h)
description: The RemoveRADIUSServer_IN structure holds the input data for the user-mode RemoveRADIUSServer method, which is used to remove a RADIUS server entry.
old-location: storage\removeradiusserver_in.htm
tech.root: storage
ms.assetid: 600916e1-37c2-4766-93d9-b7d32a542542
ms.date: 03/29/2018
ms.keywords: "*PRemoveRADIUSServer_IN, PRemoveRADIUSServer_IN, PRemoveRADIUSServer_IN structure pointer [Storage Devices], RemoveRADIUSServer_IN, RemoveRADIUSServer_IN structure [Storage Devices], _RemoveRADIUSServer_IN, iscsiop/PRemoveRADIUSServer_IN, iscsiop/RemoveRADIUSServer_IN, storage.removeradiusserver_in, structs-iSCSI_e85b2fed-4691-43c4-b71a-a81905c79564.xml"
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
-	RemoveRADIUSServer_IN
product:
- Windows
targetos: Windows
req.typenames: RemoveRADIUSServer_IN, *PRemoveRADIUSServer_IN
---

# _RemoveRADIUSServer_IN structure


## -description


The RemoveRADIUSServer_IN structure holds the input data for the user-mode <b>RemoveRADIUSServer</b> method, which is used to remove a RADIUS server entry.


## -struct-fields




### -field RADIUSIPAddress

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a> structure that specifies the address of the RADIUS server to remove.


## -remarks



It is optional that you implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564008">RemovePersistentLogin_OUT</a>
 

 

