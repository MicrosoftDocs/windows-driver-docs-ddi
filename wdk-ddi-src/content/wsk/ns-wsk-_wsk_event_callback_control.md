---
UID: NS:wsk._WSK_EVENT_CALLBACK_CONTROL
title: "_WSK_EVENT_CALLBACK_CONTROL" (wsk.h)
description: The WSK_EVENT_CALLBACK_CONTROL structure specifies the information for enabling and disabling a socket's event callback functions.
old-location: netvista\wsk_event_callback_control.htm
tech.root: netvista
ms.assetid: 152e142a-dda4-4540-b1a9-14625f4653bb
ms.date: 05/02/2018
ms.keywords: "*PWSK_EVENT_CALLBACK_CONTROL, PWSK_EVENT_CALLBACK_CONTROL, PWSK_EVENT_CALLBACK_CONTROL structure pointer [Network Drivers Starting with Windows Vista], WSK_EVENT_CALLBACK_CONTROL, WSK_EVENT_CALLBACK_CONTROL structure [Network Drivers Starting with Windows Vista], _WSK_EVENT_CALLBACK_CONTROL, netvista.wsk_event_callback_control, wsk/PWSK_EVENT_CALLBACK_CONTROL, wsk/WSK_EVENT_CALLBACK_CONTROL, wskref_22cd0a01-12fe-4e5a-a423-c3198cc5ab05.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_EVENT_CALLBACK_CONTROL
product:
- Windows
targetos: Windows
req.typenames: WSK_EVENT_CALLBACK_CONTROL, *PWSK_EVENT_CALLBACK_CONTROL
---

# _WSK_EVENT_CALLBACK_CONTROL structure


## -description


The WSK_EVENT_CALLBACK_CONTROL structure specifies the information for enabling and disabling a
  socket's event callback functions.


## -struct-fields




### -field NpiId

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
     (NPI)</a> identifier that specifies the NPI for the event callback function that is being enabled or
     disabled. For enabling or disabling any of the standard WSK event callback functions, this member is a
     pointer to the WSK NPI identifier, NPI_WSK_INTERFACE_ID. For enabling or disabling any event callback
     functions for an extension interface, this member is a pointer to the NPI identifier for the extension
     interface.


### -field EventMask

A ULONG value that contains a bitwise OR of event flags for the event callback functions that are
     being enabled or disabled. For information about the event flags for the standard WSK event callback
     functions, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a>.


## -remarks



A WSK application can enable any combination of event callback functions for a socket simultaneously
    by setting the 
    <b>EventMask</b> member to a bitwise OR of the event flags for all of the event callback functions that
    are being enabled. However, a WSK application must disable event callback functions individually by
    setting the 
    <b>EventMask</b> member to a bitwise OR of the event flag for the event callback function that is being
    disabled and the WSK_EVENT_DISABLE flag.

For more information about statically enabling certain event callback functions for all of the sockets
    that are created by a WSK application, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571181">
    WSK_SET_STATIC_EVENT_CALLBACKS</a>.

For more information about enabling and disabling a socket's event callback functions, see 
    <a href="https://msdn.microsoft.com/library/windows/desktop/aa363707">Enabling and
    Disabling Event Callback Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571181">
   WSK_SET_STATIC_EVENT_CALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>
 

 

