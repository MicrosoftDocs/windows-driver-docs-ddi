---
UID: NS:iscsiop._RemoveiSNSServer_OUT
title: "_RemoveiSNSServer_OUT"
author: windows-driver-content
description: The RemoveiSNSServer_OUT structure holds the output data for the user-mode RemoveISNSServer method.
old-location: storage\removeisnsserver_out.htm
old-project: storage
ms.assetid: 42866b25-280c-492c-8e98-1a04a46561a4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: RemoveiSNSServer_OUT, PRemoveiSNSServer_OUT, *PRemoveiSNSServer_OUT, PRemoveiSNSServer_OUT structure pointer [Storage Devices], iscsiop/RemoveiSNSServer_OUT, RemoveiSNSServer_OUT structure [Storage Devices], structs-iSCSI_8d8df1a1-3b89-42a1-9ef8-3e749a94b531.xml, _RemoveiSNSServer_OUT, storage.removeisnsserver_out, iscsiop/PRemoveiSNSServer_OUT
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
-	RemoveiSNSServer_OUT
product: Windows
targetos: Windows
req.typenames: "*PRemoveiSNSServer_OUT, RemoveiSNSServer_OUT"
---

# _RemoveiSNSServer_OUT structure


## -description


The RemoveiSNSServer_OUT structure holds the output data for the user-mode <b>RemoveISNSServer</b> method.


## -syntax


````
typedef struct _RemoveiSNSServer_OUT {
  ULONG Status;
} RemoveiSNSServer_OUT, *PRemoveiSNSServer_OUT;
````


## -struct-fields




### -field Status

On output from <b>RemoveISNSServer</b>, the status of the operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks


It is optional that you implement this method.



## -see-also

<a href="..\iscsiop\ns-iscsiop-_removeisnsserver_in.md">RemoveiSNSServer_IN</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveiSNSServer_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

