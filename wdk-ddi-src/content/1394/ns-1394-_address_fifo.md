---
UID: NS:1394._ADDRESS_FIFO
title: "_ADDRESS_FIFO"
author: windows-driver-content
description: The ADDRESS_FIFO structure is an entry in a singly-linked list of MDLs used by the REQUEST_ALLOCATE_ADDRESS_RANGE IEEE 1394 bus request.
old-location: ieee\address_fifo.htm
old-project: IEEE
ms.assetid: df2b6438-271d-4ea2-a06b-49a83415ca7a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PADDRESS_FIFO, PADDRESS_FIFO structure pointer [Buses], ADDRESS_FIFO, 1394stct_bf7f3e1b-88a4-4c37-88ee-cf5d69595988.xml, ADDRESS_FIFO structure [Buses], 1394/ADDRESS_FIFO, 1394/PADDRESS_FIFO, _ADDRESS_FIFO, IEEE.address_fifo, PADDRESS_FIFO"
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
-	ADDRESS_FIFO
product: Windows
targetos: Windows
req.typenames: ADDRESS_FIFO, *PADDRESS_FIFO
---

# _ADDRESS_FIFO structure


## -description


The ADDRESS_FIFO structure is an entry in a singly-linked list of MDLs used by the REQUEST_ALLOCATE_ADDRESS_RANGE IEEE 1394 bus request.


## -syntax


````
typedef struct _ADDRESS_FIFO {
  SLIST_ENTRY FifoList;
  PMDL        FifoMdl;
} ADDRESS_FIFO, *PADDRESS_FIFO;
````


## -struct-fields




### -field FifoList

Specifies the rest of the list. This is a singly linked list. 


### -field FifoMdl

Specifies the MDL for the FIFO element described by this entry of the list.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537437">NOTIFICATION_INFO</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20ADDRESS_FIFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

