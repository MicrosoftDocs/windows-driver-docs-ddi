---
UID: NS:bdatypes._BDA_TEMPLATE_CONNECTION
title: "_BDA_TEMPLATE_CONNECTION"
author: windows-driver-content
description: The BDA_TEMPLATE_CONNECTION structure describes the template for a BDA connection in terms of where it begins and ends.
old-location: stream\bda_template_connection.htm
tech.root: stream
ms.assetid: f3b5d06d-0557-49a8-9c0d-be964203108a
ms.date: 4/23/2018
ms.keywords: "*PBDA_TEMPLATE_CONNECTION, BDA_TEMPLATE_CONNECTION, BDA_TEMPLATE_CONNECTION structure [Streaming Media Devices], PBDA_TEMPLATE_CONNECTION, PBDA_TEMPLATE_CONNECTION structure pointer [Streaming Media Devices], _BDA_TEMPLATE_CONNECTION, bdaref_fbba4f2e-dd43-4f5c-b057-f1fbc52cfbe9.xml, bdatypes/BDA_TEMPLATE_CONNECTION, bdatypes/PBDA_TEMPLATE_CONNECTION, stream.bda_template_connection"
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
-	bdatypes.h
api_name:
-	BDA_TEMPLATE_CONNECTION
product:
- Windows
targetos: Windows
req.typenames: BDA_TEMPLATE_CONNECTION, *PBDA_TEMPLATE_CONNECTION
---

# _BDA_TEMPLATE_CONNECTION structure


## -description


The BDA_TEMPLATE_CONNECTION structure describes the template for a BDA connection in terms of where it begins and ends. 


## -struct-fields




### -field FromNodeType

Index of the element in the zero-based array of internal node types (KSNODE_DESCRIPTOR array) that indicates the node type where the connection begins or −1 to indicate that the connection begins at an upstream filter. 


### -field FromNodePinType

Index of the element in the zero-based array of pin types (KSPIN_DESCRIPTOR_EX array) that indicates the pin type where the connection begins. The array of pin types is the list of pin types that are available in the filter's template topology. 


### -field ToNodeType

Index of the element in the zero-based array of internal node types (KSNODE_DESCRIPTOR array) that indicates the node type where the connection ends or −1 to indicate that the connection ends at a downstream filter. 


### -field ToNodePinType

Index of the element in the zero-based array of pin types (KSPIN_DESCRIPTOR_EX array) that indicates the pin type where the connection ends. The array of pin types is the list of pin types that are available in the filter's template topology. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556544">BDA_PIN_PAIRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556501">BdaPropertyTemplateConnections</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563473">KSNODE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567148">KSTOPOLOGY_CONNECTION</a>
 

 

