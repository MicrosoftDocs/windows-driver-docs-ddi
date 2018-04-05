---
UID: NS:wsk._WSK_DATAGRAM_INDICATION
title: "_WSK_DATAGRAM_INDICATION"
author: windows-driver-content
description: The WSK_DATAGRAM_INDICATION structure describes a datagram that has been received on a datagram socket.
old-location: netvista\wsk_datagram_indication.htm
old-project: netvista
ms.assetid: 061db3ca-80ed-419e-8cca-f49d1498b780
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWSK_DATAGRAM_INDICATION, PWSK_DATAGRAM_INDICATION, PWSK_DATAGRAM_INDICATION structure pointer [Network Drivers Starting with Windows Vista], WSK_DATAGRAM_INDICATION, WSK_DATAGRAM_INDICATION structure [Network Drivers Starting with Windows Vista], _WSK_DATAGRAM_INDICATION, netvista.wsk_datagram_indication, wsk/PWSK_DATAGRAM_INDICATION, wsk/WSK_DATAGRAM_INDICATION, wskref_1e0fb168-6e03-4b73-8bb4-e3bce0c94b02.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_DATAGRAM_INDICATION
product:
- Windows
targetos: Windows
req.typenames: WSK_DATAGRAM_INDICATION, *PWSK_DATAGRAM_INDICATION
req.product: Windows 10 or later.
---

# _WSK_DATAGRAM_INDICATION structure


## -description


The WSK_DATAGRAM_INDICATION structure describes a datagram that has been received on a datagram
  socket.


## -struct-fields




### -field Next

A pointer to the next WSK_DATAGRAM_INDICATION structure in a linked list of
     WSK_DATAGRAM_INDICATION structures. If this member is <b>NULL</b>, this structure is the last
     WSK_DATAGRAM_INDICATION structure in the linked list.


### -field Buffer

A WSK_BUF structure that describes a datagram that has been received on the socket.


### -field ControlInfo

The control information that is associated with the received datagram. The control information
     data that is associated with a datagram is made up of one or more control data objects, each of which
     begins with a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a> structure. If there is no control
     information present for the received datagram, this member is <b>NULL</b>.


### -field ControlInfoLength

The size of the control information that is associated with the received datagram. If this value
     is zero, there is no control information present for the datagram.


### -field RemoteAddress

A pointer to a buffer that contains the remote transport address from which the received datagram
     originated. The buffer contains the specific SOCKADDR structure type that corresponds to the address
     family that the WSK application specified when it created the datagram socket.


## -remarks



The WSK subsystem passes a pointer to a WSK_DATAGRAM_INDICATION structure as the 
    <i>DataIndication</i> parameter when it calls a datagram socket's 
    <a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a> event callback
    function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544964">CMSGHDR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571153">WSK_BUF</a>



<a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571144">WskRelease</a>
 

 

