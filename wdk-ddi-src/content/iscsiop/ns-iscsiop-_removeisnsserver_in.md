---
UID: NS:iscsiop._RemoveiSNSServer_IN
title: "_RemoveiSNSServer_IN"
author: windows-driver-content
description: The RemoveiSNSServer_IN structure holds the input data for the user-mode RemoveISNSServer method, which is used to remove an iSNS server entry.
old-location: storage\removeisnsserver_in.htm
old-project: storage
ms.assetid: 10e72834-4866-42f2-842e-0a30278acab8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PRemoveiSNSServer_IN, PRemoveiSNSServer_IN, PRemoveiSNSServer_IN structure pointer [Storage Devices], RemoveiSNSServer_IN, RemoveiSNSServer_IN structure [Storage Devices], _RemoveiSNSServer_IN, iscsiop/PRemoveiSNSServer_IN, iscsiop/RemoveiSNSServer_IN, storage.removeisnsserver_in, structs-iSCSI_b79fe0e4-386c-4b5c-9b43-ef8fdb7f4b6a.xml"
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
-	RemoveiSNSServer_IN
product: Windows
targetos: Windows
req.typenames: RemoveiSNSServer_IN, *PRemoveiSNSServer_IN
---

# _RemoveiSNSServer_IN structure


## -description


The RemoveiSNSServer_IN structure holds the input data for the user-mode <b>RemoveISNSServer</b> method, which is used to remove an iSNS server entry.


## -struct-fields




### -field iSNSServerName

The name of the iSNS server to remove from the initiator's list.


## -remarks



It is optional that you implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563982">RemoveiSNSServer_OUT</a>
 

 

