---
UID: NS:wsk._WSK_INSPECT_ID
title: "_WSK_INSPECT_ID"
author: windows-driver-content
description: The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a listening socket.
old-location: netvista\wsk_inspect_id.htm
old-project: netvista
ms.assetid: 54578dc5-a88f-4649-adbd-6a5e1e31e7b3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWSK_INSPECT_ID, PWSK_INSPECT_ID, PWSK_INSPECT_ID structure pointer [Network Drivers Starting with Windows Vista], WSK_INSPECT_ID, WSK_INSPECT_ID structure [Network Drivers Starting with Windows Vista], _WSK_INSPECT_ID, netvista.wsk_inspect_id, wsk/PWSK_INSPECT_ID, wsk/WSK_INSPECT_ID, wskref_7e500c2a-23ce-4193-b8a5-fbf416a9659d.xml"
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
-	WSK_INSPECT_ID
product: Windows
targetos: Windows
req.typenames: WSK_INSPECT_ID, *PWSK_INSPECT_ID
req.product: Windows 10 or later.
---

# _WSK_INSPECT_ID structure


## -description


The WSK_INSPECT_ID structure specifies an identifier for an incoming connection request on a
  listening socket.


## -struct-fields




### -field Key

A key that is assigned to the incoming connection request.


### -field SerialNumber

A serial number that is assigned to the incoming connection request.


## -remarks



The WSK subsystem passes a pointer to a WSK_INSPECT_ID structure to a WSK application's 
    <a href="https://msdn.microsoft.com/40f184ac-4ef3-485a-a529-71c1f2716427">WskInspectEvent</a> event callback function
    whenever an incoming connection request arrives on a listening socket that has conditional accept mode
    enabled. The contents of the WSK_INSPECT_ID structure uniquely identify the incoming connection
    request.

If the WSK application returns 
    <b>WskInspectPend</b> from a call to its 
    <i>WskInspectEvent</i> event callback function, the application must first copy the 
    <u>contents</u> of the WSK_INSPECT_ID structure that is provided by the WSK subsystem into its own
    WSK_INSPECT_ID structure. The WSK application then passes a pointer to its WSK_INSPECT_ID structure to
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a> function when it
    completes the inspection.

If the incoming connection request is dropped by the remote system while an inspect operation is
    pending, the WSK subsystem calls the WSK application's 
    <a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a> event callback function with a
    pointer to a WSK_INSPECT_ID structure that identifies the dropped request. The WSK application uses the
    contents of this WSK_INSPECT_ID structure to determine which inspection of an incoming connection request
    should be terminated. The WSK application should compare the contents of the WSK_INSPECT_ID structures to
    check for a match. The actual values of the structure members are irrelevant.

A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/listening-for-and-accepting-incoming-connections">Listening for and
    Accepting Incoming Connections</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a>



<a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a>



<a href="https://msdn.microsoft.com/40f184ac-4ef3-485a-a529-71c1f2716427">WskInspectEvent</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_INSPECT_ID structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

