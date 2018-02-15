---
UID: NS:ks.KSP_NODE
title: KSP_NODE
author: windows-driver-content
description: Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request.
old-location: stream\ksp_node.htm
old-project: stream
ms.assetid: 2d5f1b31-d8fe-40a3-ac23-cc442f3adbe5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSP_NODE, ks/KSP_NODE, KSP_NODE structure [Streaming Media Devices], stream.ksp_node, ks-struct_e93685c5-c84a-469a-ad2c-2407cb2e383b.xml, PKSP_NODE structure pointer [Streaming Media Devices], KSP_NODE, PKSP_NODE, ks/PKSP_NODE"
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
-	KSP_NODE
product: Windows
targetos: Windows
req.typenames: "*PKSP_NODE, KSP_NODE"
---

# KSP_NODE structure


## -description


Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      NodeId;
  ULONG      Reserved;
} KSP_NODE, *PKSP_NODE;
````


## -struct-fields




### -field Property

Specifies a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure.


### -field NodeId

Specifies the node ID.


### -field Reserved

Reserved for system use. Should be set to zero.


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksnodeproperty.md">KSNODEPROPERTY</a>



<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSP_NODE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

