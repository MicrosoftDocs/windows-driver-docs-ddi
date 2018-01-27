---
UID: NS:ks.KSTOPOLOGY_CONNECTION
title: KSTOPOLOGY_CONNECTION
author: windows-driver-content
description: The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter.
old-location: stream\kstopology_connection.htm
old-project: stream
ms.assetid: 604be66a-bec7-48db-b038-aaaf78043965
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks-struct_b688f291-7064-492b-8ab6-5f167941ebbf.xml, ks/KSTOPOLOGY_CONNECTION, *PKSTOPOLOGY_CONNECTION, KSTOPOLOGY_CONNECTION structure [Streaming Media Devices], PKSTOPOLOGY_CONNECTION, ks/PKSTOPOLOGY_CONNECTION, PKSTOPOLOGY_CONNECTION structure pointer [Streaming Media Devices], stream.kstopology_connection, KSTOPOLOGY_CONNECTION
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
-	KSTOPOLOGY_CONNECTION
product: Windows
targetos: Windows
req.typenames: *PKSTOPOLOGY_CONNECTION, KSTOPOLOGY_CONNECTION
---

# KSTOPOLOGY_CONNECTION structure


## -description


The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter.


## -syntax


````
typedef struct {
  ULONG FromNode;
  ULONG FromNodePin;
  ULONG ToNode;
  ULONG ToNodePin;
} KSTOPOLOGY_CONNECTION, *PKSTOPOLOGY_CONNECTION;
````


## -struct-fields




### -field FromNode

Specifies the node ID of the node on the upstream end of the connection. If this end of the connection is an external pin on the filter -- not a logical pin on a node--set this member to the null node-ID value, KSFILTER_NODE.


### -field FromNodePin

Specifies the pin ID for the upstream end of the connection. If <b>FromNode </b>is KSFILTER_NODE, the pin on this end of the connection is an external pin on the filter. If not, the pin on this end is a logical pin on an internal node.


### -field ToNode

Specifies the node ID of the node on the downstream end of the connection. If this end of the connection is an external pin on the filter--not a logical pin on a node -- set this member to the null node-ID value, KSFILTER_NODE.


### -field ToNodePin

Specifies the pin ID for the downstream end of the connection. If <b>ToNode</b> is KSFILTER_NODE, the pin on this end of the connection is an external pin on the filter. If not, the pin on this end is a logical pin on an internal node.


## -remarks


KSTOPOLOGY_CONNECTION represents a single connection inside a filter, between either external pins, internal nodes, or an external pin and an internal node.

A streaming driver returns an array of KSTOPOLOGY_CONNECTION structures in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565802">KSPROPERTY_TOPOLOGY_CONNECTIONS</a> get-property request.

When representing a connection between two external pins, both <b>FromNode</b> and <b>ToNode</b> should be set to KSFILTER_NODE, and the <b>FromNodePin</b> and <b>ToNodePin</b> should be the pin type ID of the respective pins. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a> for a description of pin type IDs.)

Otherwise, <b>FromNodePin</b> or <b>ToNodePin</b> represent a logical incoming or outgoing pin for the connection. The logical pin numbers are used solely to describe a connection between nodes; they have no existence outside of the KSPROPERTY_TOPOLOGY_CONNECTIONS property.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a> structure name is an alias for KSTOPOLOGY_CONNECTION.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537688">PCCONNECTION_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566598">KSPROPSETID_Topology</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565802">KSPROPERTY_TOPOLOGY_CONNECTIONS</a>

<a href="..\bdasup\nf-bdasup-bdapropertytemplateconnections.md">BdaPropertyTemplateConnections</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSTOPOLOGY_CONNECTION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

