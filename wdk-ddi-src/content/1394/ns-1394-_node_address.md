---
UID: NS:1394._NODE_ADDRESS
title: "_NODE_ADDRESS"
author: windows-driver-content
description: The NODE_ADDRESS structure specifies the 10-bit bus number and 6-bit node number that serve as the node address for a 1394 node.
old-location: ieee\node_address.htm
old-project: IEEE
ms.assetid: ecafa166-356e-48d6-84c4-0f0c339289ac
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PNODE_ADDRESS structure pointer [Buses], PNODE_ADDRESS, NODE_ADDRESS, *PNODE_ADDRESS, _NODE_ADDRESS, IEEE.node_address, 1394/PNODE_ADDRESS, 1394stct_4b87009c-620b-4840-aea3-52e059d388cd.xml, NODE_ADDRESS structure [Buses], 1394/NODE_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
-	1394.h
apiname:
-	NODE_ADDRESS
product: Windows
targetos: Windows
req.typenames: NODE_ADDRESS, *PNODE_ADDRESS
---

# _NODE_ADDRESS structure


## -description


The NODE_ADDRESS structure specifies the 10-bit bus number and 6-bit node number that serve as the node address for a 1394 node.


## -syntax


````
typedef struct _NODE_ADDRESS {
  USHORT NA_Node_Number  :6;
  USHORT NA_Bus_Number  :10;
} NODE_ADDRESS, *PNODE_ADDRESS;
````


## -struct-fields




### -field NA_Node_Number

Specifies the 6-bit node number. This member contains bits 10-15 of the node address.


### -field NA_Bus_Number

Specifies the 10-bit bus number. This member specifies bits 0-10 of the node address. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537020">BUS_GENERATION_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537346">IO_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20NODE_ADDRESS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

