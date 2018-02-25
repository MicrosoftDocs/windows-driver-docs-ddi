---
UID: NS:bdamedia._KSP_BDA_NODE_PIN
title: "_KSP_BDA_NODE_PIN"
author: windows-driver-content
description: The KSP_BDA_NODE_PIN structure describes a property request to retrieve the controlling pin for a node.
old-location: stream\ksp_bda_node_pin.htm
old-project: stream
ms.assetid: 684a0b26-0e25-44fb-bca9-c86ac029b3b8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSP_BDA_NODE_PIN, ,, A, B, D, E, I, K, KSP_BDA_NODE_PIN, KSP_BDA_NODE_PIN structure [Streaming Media Devices], N, O, P, PKSP_BDA_NODE_PIN, PKSP_BDA_NODE_PIN structure pointer [Streaming Media Devices], S, _, _KSP_BDA_NODE_PIN, bdamedia/KSP_BDA_NODE_PIN, bdamedia/PKSP_BDA_NODE_PIN, bdaref_5e3a84db-906c-4d12-863d-9a77b2f7d78c.xml, stream.ksp_bda_node_pin"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	bdamedia.h
apiname:
-	KSP_BDA_NODE_PIN
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# _KSP_BDA_NODE_PIN structure


## -description


The KSP_BDA_NODE_PIN structure describes a property request to retrieve the controlling pin for a node. 


## -syntax


````
typedef struct _KSP_BDA_NODE_PIN {
  KSPROPERTY Property;
  ULONG      ulNodeType;
  ULONG      ulInputPinId;
  ULONG      ulOutputPinId;
} KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN;
````


## -struct-fields




### -field Property

KSPROPERTY structure that describes the property and request type of the property request.


### -field ulNodeType

Index of the element in the zero-based array of internal node types (KSNODE_DESCRIPTOR array) that specifies the node type for which to retrieve the controlling pin. 


### -field ulInputPinId

Identifier of an input pin of the filter.


### -field ulOutputPinId

Identifier of an output pin of the filter.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



<a href="..\ks\ns-ks-_ksnode_descriptor.md">KSNODE_DESCRIPTOR</a>



<a href="..\bdasup\nf-bdasup-bdapropertygetcontrollingpinid.md">BdaPropertyGetControllingPinId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSP_BDA_NODE_PIN structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

