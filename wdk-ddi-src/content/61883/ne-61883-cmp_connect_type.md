---
UID: NE:61883.CMP_CONNECT_TYPE
title: CMP_CONNECT_TYPE
author: windows-driver-content
description: This enumeration specifies a connection type.
old-location: ieee\cmp_connect_type.htm
old-project: IEEE
ms.assetid: 8C206071-2616-4BFB-B7CA-E872CC8D5405
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 61883/CMP_Broadcast, 61883/CMP_CONNECT_TYPE, 61883/CMP_PointToPoint, CMP_Broadcast, CMP_CONNECT_TYPE, CMP_CONNECT_TYPE enumeration [Buses], CMP_PointToPoint, IEEE.cmp_connect_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: 61883.h
req.include-header: 
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
-	61883.h
apiname:
-	CMP_CONNECT_TYPE
product: Windows
targetos: Windows
req.typenames: CMP_CONNECT_TYPE
---

# CMP_CONNECT_TYPE enumeration


## -description


This enumeration specifies a connection type. 


## -syntax


````
typedef enum  { 
  CMP_Broadcast     = 0,
  CMP_PointToPoint
} CMP_CONNECT_TYPE;
````


## -enum-fields




### -field CMP_Broadcast

Indicates that this is a broadcast connection.


### -field CMP_PointToPoint

Indicates that this is a point-to-point connection.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_CONNECT_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

