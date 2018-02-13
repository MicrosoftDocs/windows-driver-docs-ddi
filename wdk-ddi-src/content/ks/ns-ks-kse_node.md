---
UID: NS:ks.KSE_NODE
title: KSE_NODE
author: windows-driver-content
description: The KSE_NODE structure specifies an event request on a specific node.
old-location: stream\kse_node.htm
old-project: stream
ms.assetid: 89446165-cdc3-414d-bcce-f2c978d94547
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSE_NODE structure [Streaming Media Devices], ks/KSE_NODE, PKSE_NODE structure pointer [Streaming Media Devices], KSE_NODE, ks/PKSE_NODE, PKSE_NODE, *PKSE_NODE, ks-struct_701a51ab-90d7-47d6-8e40-bd30d0ddd7b9.xml, stream.kse_node
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSE_NODE
product: Windows
targetos: Windows
req.typenames: "*PKSE_NODE, KSE_NODE"
---

# KSE_NODE structure


## -description


The KSE_NODE structure specifies an event request on a specific node.


## -syntax


````
typedef struct {
  KSEVENT Event;
  ULONG   NodeId;
  ULONG   Reserved;
} KSE_NODE, *PKSE_NODE;
````


## -struct-fields




### -field Event

A structure of type <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> that identifies the requested event.


### -field NodeId

Specifies the node ID.


### -field Reserved

Reserved for system use. Should be set to zero.


## -see-also

<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSE_NODE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

