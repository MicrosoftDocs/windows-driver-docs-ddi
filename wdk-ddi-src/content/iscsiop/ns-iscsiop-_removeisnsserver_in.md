---
UID: NS:iscsiop._RemoveiSNSServer_IN
title: "_RemoveiSNSServer_IN"
author: windows-driver-content
description: The RemoveiSNSServer_IN structure holds the input data for the user-mode RemoveISNSServer method, which is used to remove an iSNS server entry.
old-location: storage\removeisnsserver_in.htm
old-project: storage
ms.assetid: 10e72834-4866-42f2-842e-0a30278acab8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PRemoveiSNSServer_IN, iscsiop/PRemoveiSNSServer_IN, PRemoveiSNSServer_IN structure pointer [Storage Devices], RemoveiSNSServer_IN structure [Storage Devices], iscsiop/RemoveiSNSServer_IN, PRemoveiSNSServer_IN, RemoveiSNSServer_IN, storage.removeisnsserver_in, _RemoveiSNSServer_IN, structs-iSCSI_b79fe0e4-386c-4b5c-9b43-ef8fdb7f4b6a.xml"
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
-	RemoveiSNSServer_IN
product: Windows
targetos: Windows
req.typenames: RemoveiSNSServer_IN, *PRemoveiSNSServer_IN
---

# _RemoveiSNSServer_IN structure


## -description


The RemoveiSNSServer_IN structure holds the input data for the user-mode <b>RemoveISNSServer</b> method, which is used to remove an iSNS server entry.


## -syntax


````
typedef struct _RemoveiSNSServer_IN {
  WCHAR iSNSServerName[223 + 1];
} RemoveiSNSServer_IN, *PRemoveiSNSServer_IN;
````


## -struct-fields




### -field iSNSServerName

The name of the iSNS server to remove from the initiator's list.


## -remarks



It is optional that you implement this method.




## -see-also

<a href="..\iscsiop\ns-iscsiop-_removeisnsserver_out.md">RemoveiSNSServer_OUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveiSNSServer_IN structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

