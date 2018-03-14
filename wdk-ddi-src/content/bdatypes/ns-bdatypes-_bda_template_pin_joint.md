---
UID: NS:bdatypes._BDA_TEMPLATE_PIN_JOINT
title: "_BDA_TEMPLATE_PIN_JOINT"
author: windows-driver-content
description: The BDA_TEMPLATE_PIN_JOINT structure describes a joint in a template topology.
old-location: stream\bda_template_pin_joint.htm
old-project: stream
ms.assetid: 83df4c9e-7122-4087-9d03-98f2eeed4ec4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_TEMPLATE_PIN_JOINT, BDA_TEMPLATE_PIN_JOINT, BDA_TEMPLATE_PIN_JOINT structure [Streaming Media Devices], PBDA_TEMPLATE_PIN_JOINT, PBDA_TEMPLATE_PIN_JOINT structure pointer [Streaming Media Devices], _BDA_TEMPLATE_PIN_JOINT, bdaref_d1704bcd-5d90-4fa2-b675-509f31737dd4.xml, bdatypes/BDA_TEMPLATE_PIN_JOINT, bdatypes/PBDA_TEMPLATE_PIN_JOINT, stream.bda_template_pin_joint"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bdatypes.h
api_name:
-	BDA_TEMPLATE_PIN_JOINT
product: Windows
targetos: Windows
req.typenames: BDA_TEMPLATE_PIN_JOINT, *PBDA_TEMPLATE_PIN_JOINT
---

# _BDA_TEMPLATE_PIN_JOINT structure


## -description


The BDA_TEMPLATE_PIN_JOINT structure describes a joint in a template topology. 


## -syntax


````
typedef struct _BDA_TEMPLATE_PIN_JOINT {
  ULONG uliTemplateConnection;
  ULONG ulcInstancesMax;
} BDA_TEMPLATE_PIN_JOINT, *PBDA_TEMPLATE_PIN_JOINT;
````


## -struct-fields




### -field uliTemplateConnection

Index of an element in a array of template connections (KSTOPOLOGY_CONNECTION or BDA_TEMPLATE_CONNECTION array) that represents the joint.


### -field ulcInstancesMax

Maximum number of possible instances of the joint in the template topology.


## -see-also

<a href="..\ks\ns-ks-kstopology_connection.md">KSTOPOLOGY_CONNECTION</a>



<a href="..\bdatypes\ns-bdatypes-_bda_template_connection.md">BDA_TEMPLATE_CONNECTION</a>



 

 


