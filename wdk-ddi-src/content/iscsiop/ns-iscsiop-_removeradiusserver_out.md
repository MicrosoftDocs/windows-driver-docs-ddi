---
UID: NS:iscsiop._RemoveRADIUSServer_OUT
title: "_RemoveRADIUSServer_OUT"
author: windows-driver-content
description: The RemoveiSNSServer_OUT structure holds the output data for the RemoveRADIUSServer method.
old-location: storage\removeradiusserver_out.htm
old-project: storage
ms.assetid: da5be900-a362-4d74-9ac7-65b96f0348ce
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PRemoveRADIUSServer_OUT, PRemoveRADIUSServer_OUT, PRemoveRADIUSServer_OUT structure pointer [Storage Devices], RemoveRADIUSServer_OUT, RemoveRADIUSServer_OUT structure [Storage Devices], _RemoveRADIUSServer_OUT, iscsiop/PRemoveRADIUSServer_OUT, iscsiop/RemoveRADIUSServer_OUT, storage.removeradiusserver_out, structs-iSCSI_dea5813a-b7e8-4702-af57-f7a40360efb9.xml"
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
-	RemoveRADIUSServer_OUT
product: Windows
targetos: Windows
req.typenames: RemoveRADIUSServer_OUT, *PRemoveRADIUSServer_OUT
---

# _RemoveRADIUSServer_OUT structure


## -description


The RemoveiSNSServer_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564020">RemoveRADIUSServer</a> method.


## -syntax


````
typedef struct _RemoveRADIUSServer_OUT {
  ULONG Status;
} RemoveRADIUSServer_OUT, *PRemoveRADIUSServer_OUT;
````


## -struct-fields




### -field Status

On output from <b>RemoveRADIUSServer</b>, the status of the operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



It is optional that you implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564020">RemoveRADIUSServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="..\iscsiop\ns-iscsiop-_removeradiusserver_in.md">RemoveRADIUSServer_IN</a>



 

 


