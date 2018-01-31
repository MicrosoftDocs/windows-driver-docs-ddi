---
UID: NS:bthddi._BRB_SCO_REGISTER_SERVER
title: "_BRB_SCO_REGISTER_SERVER"
author: windows-driver-content
description: A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable of receiving SCO connections from remote Bluetooth devices.
old-location: bltooth\_brb_sco_register_server.htm
old-project: bltooth
ms.assetid: c7d7a70d-f84b-4937-ac7b-297016d01d42
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_BRB_SCO_REGISTER_SERVER, bltooth._brb_sco_register_server, bthddi/_BRB_SCO_REGISTER_SERVER, _BRB_SCO_REGISTER_SERVER structure [Bluetooth Devices], bth_structs_332b94af-3e05-4adb-9e89-4933e119df51.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	_BRB_SCO_REGISTER_SERVER
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_REGISTER_SERVER structure


## -description


A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable
  of receiving SCO connections from remote Bluetooth devices.


## -syntax


````
struct _BRB_SCO_REGISTER_SERVER {
  BRB_HEADER                 Hdr;
  BTH_ADDR                   BtAddress;
  ULONG                      Reserved;
  ULONG                      IndicationFlags;
  PFNSCO_INDICATION_CALLBACK IndicationCallback;
  PVOID                      IndicationCallbackContext;
  PVOID                      ReferenceObject;
  SCO_SERVER_HANDLE          ServerHandle;
};
````


## -struct-fields




#### - Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


#### - BtAddress

The address of the remote Bluetooth device for which to receive notifications.


#### - Reserved

Reserved for future use. Do not use.


#### - IndicationFlags

A flag that indicates when the callback function that is specified in the 
     <b>IndicationCallback</b> member should be called. The following flags are defined.
     
<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
SCO_INDICATION_SCO_REQUEST

</td>
<td>
Notify the profile driver if there are any incoming SCO connections.

</td>
</tr>
<tr>
<td>
SCO_INDICATION_ESCO_REQUEST

</td>
<td>
Notify the profile driver if there are any incoming eSCO connections.

</td>
</tr>
</table> 


#### - IndicationCallback

A 
     <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>, implemented
     by the profile driver, that the Bluetooth driver stack should call to notify the profile driver about
     incoming SCO connections.


#### - IndicationCallbackContext

The context passed to the function that is defined in the 
     <b>IndicationCallback</b> member.


#### - ReferenceObject

A pointer to an object to pass to the 
     <a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a> and 
     <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> functions to
     maintain a reference count of. Profile drivers should provide this object in such a way that the
     Bluetooth driver stack can increase the count of the object for as long as the driver stack can call the
     callback function specified in the 
     <b>IndicationCallback</b> member. The Bluetooth driver stack will decrease the reference count of the
     object when the profile driver 
     <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">builds and sends</a> a 
     <mshelp:link keywords="bltooth.brb_sco_unregister_server" tabindex="0"><b>
     BRB_SCO_UNREGISTER_SERVER</b></mshelp:link> request.


#### - ServerHandle

Handle to the SCO server, if successfully returned. When the profile driver should no longer
     receive remote connect indications it should pass this handle to 
     <mshelp:link keywords="bltooth.brb_sco_unregister_server" tabindex="0"><b>
     BRB_SCO_UNREGISTER_SERVER</b></mshelp:link>.


## -remarks


To register itself as a SCO server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536628">BRB_SCO_REGISTER_SERVER</a> request.

If successful, the Bluetooth driver stack can then notify the profile driver when remote devices
    attempt to create a SCO connection to the profile driver.

After the profile driver has registered itself, the Bluetooth driver stack can notify it when a remote
    device attempts to connect to it by calling the 
    <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a> that the
    profile driver implements and specifies in the 
    <b>IndicationCallback</b> member.

When the profile driver receives notification of a connection attempt, it should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <mshelp:link keywords="bltooth.brb_sco_open_channel_response" tabindex="0"><b>
    BRB_SCO_OPEN_CHANNEL_RESPONSE</b></mshelp:link> request to either accept or reject the connection attempt. For more
    information about accepting or rejecting SCO connection attempts, see the 
    <a href="..\bthddi\ns-bthddi-_brb_sco_open_channel.md">_BRB_SCO_OPEN_CHANNEL</a> structure.

After a connection is established, the profile driver can issue other BRBs to communicate with the
    remote device.

To stop receiving remote connection notifications, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <mshelp:link keywords="bltooth.brb_sco_unregister_server" tabindex="0"><b>
    BRB_SCO_UNREGISTER_SERVER</b></mshelp:link> request.



## -see-also

<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>

<a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536628">BRB_SCO_REGISTER_SERVER</a>

<a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536630">BRB_SCO_UNREGISTER_SERVER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_REGISTER_SERVER structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

