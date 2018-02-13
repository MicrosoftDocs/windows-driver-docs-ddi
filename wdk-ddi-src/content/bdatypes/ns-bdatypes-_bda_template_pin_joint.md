---
UID: NS:bdatypes._BDA_TEMPLATE_PIN_JOINT
title: "_BDA_TEMPLATE_PIN_JOINT"
author: windows-driver-content
description: The BDA_TEMPLATE_PIN_JOINT structure describes a joint in a template topology.
old-location: stream\bda_template_pin_joint.htm
old-project: stream
ms.assetid: 83df4c9e-7122-4087-9d03-98f2eeed4ec4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBDA_TEMPLATE_PIN_JOINT, _BDA_TEMPLATE_PIN_JOINT, BDA_TEMPLATE_PIN_JOINT, bdaref_d1704bcd-5d90-4fa2-b675-509f31737dd4.xml, BDA_TEMPLATE_PIN_JOINT structure [Streaming Media Devices], stream.bda_template_pin_joint, bdatypes/PBDA_TEMPLATE_PIN_JOINT, *PBDA_TEMPLATE_PIN_JOINT, PBDA_TEMPLATE_PIN_JOINT structure pointer [Streaming Media Devices], bdatypes/BDA_TEMPLATE_PIN_JOINT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bdatypes.h
apiname:
-	BDA_TEMPLATE_PIN_JOINT
product: Windows
targetos: Windows
req.typenames: "*PBDA_TEMPLATE_PIN_JOINT, BDA_TEMPLATE_PIN_JOINT"
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_TEMPLATE_PIN_JOINT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

