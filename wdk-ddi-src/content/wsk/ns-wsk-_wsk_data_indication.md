---
UID: NS:wsk._WSK_DATA_INDICATION
title: "_WSK_DATA_INDICATION"
author: windows-driver-content
description: The WSK_DATA_INDICATION structure describes data that has been received on a connection-oriented socket.
old-location: netvista\wsk_data_indication.htm
old-project: netvista
ms.assetid: 10af500f-bb3b-427f-86b1-ee075ffc7ac6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWSK_DATA_INDICATION, wsk/WSK_DATA_INDICATION, netvista.wsk_data_indication, PWSK_DATA_INDICATION structure pointer [Network Drivers Starting with Windows Vista], WSK_DATA_INDICATION structure [Network Drivers Starting with Windows Vista], wsk/PWSK_DATA_INDICATION, wskref_89ac35f7-4945-4b2d-90d6-177d9bca7361.xml, *PWSK_DATA_INDICATION, WSK_DATA_INDICATION, _WSK_DATA_INDICATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wsk.h
apiname:
-	WSK_DATA_INDICATION
product: Windows
targetos: Windows
req.typenames: WSK_DATA_INDICATION, *PWSK_DATA_INDICATION
req.product: Windows 10 or later.
---

# _WSK_DATA_INDICATION structure


## -description


The WSK_DATA_INDICATION structure describes data that has been received on a connection-oriented
  socket.


## -syntax


````
typedef struct _WSK_DATA_INDICATION {
  struct _WSK_DATA_INDICATION  *Next;
  WSK_BUF                     Buffer;
} WSK_DATA_INDICATION, *PWSK_DATA_INDICATION;
````


## -struct-fields




### -field Next

A pointer to the next WSK_DATA_INDICATION structure in a linked list of WSK_DATA_INDICATION
     structures. If this member is <b>NULL</b>, this structure is the last WSK_DATA_INDICATION structure in the
     linked list.


### -field _WSK_DATA_INDICATION

 


### -field Buffer

A WSK_BUF structure that describes the data that has been received on the socket.


## -remarks



The WSK subsystem passes a pointer to a WSK_DATA_INDICATION structure as the 
    <i>DataIndication</i> parameter when it calls a connection-oriented socket's 
    <a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a> event callback
    function.




## -see-also

<a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a>



<a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a>



<a href="..\wsk\nc-wsk-pfn_wsk_release_data_indication_list.md">WskRelease</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_DATA_INDICATION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

