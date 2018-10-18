---
UID: NS:bthddi._BRB_SCO_REGISTER_SERVER
title: "_BRB_SCO_REGISTER_SERVER"
author: windows-driver-content
description: A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable of receiving SCO connections from remote Bluetooth devices.
old-location: bltooth\_brb_sco_register_server.htm
tech.root: bltooth
ms.assetid: c7d7a70d-f84b-4937-ac7b-297016d01d42
ms.date: 4/27/2018
ms.keywords: "_BRB_SCO_REGISTER_SERVER, _BRB_SCO_REGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_sco_register_server, bth_structs_332b94af-3e05-4adb-9e89-4933e119df51.xml, bthddi/_BRB_SCO_REGISTER_SERVER"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_SCO_REGISTER_SERVER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_REGISTER_SERVER structure


## -description


A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable
  of receiving SCO connections from remote Bluetooth devices.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote Bluetooth device for which to receive notifications.


### -field Reserved

Reserved for future use. Do not use.


### -field IndicationFlags

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
 


### -field IndicationCallback

A 
     <a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a>, implemented
     by the profile driver, that the Bluetooth driver stack should call to notify the profile driver about
     incoming SCO connections.


### -field IndicationCallbackContext

The context passed to the function that is defined in the 
     <b>IndicationCallback</b> member.


### -field ReferenceObject

A pointer to an object to pass to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff558678">ObReferenceObject</a> and 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> functions to
     maintain a reference count of. Profile drivers should provide this object in such a way that the
     Bluetooth driver stack can increase the count of the object for as long as the driver stack can call the
     callback function specified in the 
     <b>IndicationCallback</b> member. The Bluetooth driver stack will decrease the reference count of the
     object when the profile driver 
     <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">builds and sends</a> a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536630">
     BRB_SCO_UNREGISTER_SERVER</a> request.


### -field ServerHandle

Handle to the SCO server, if successfully returned. When the profile driver should no longer
     receive remote connect indications it should pass this handle to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536630">
     BRB_SCO_UNREGISTER_SERVER</a>.


## -remarks



To register itself as a SCO server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536628">BRB_SCO_REGISTER_SERVER</a> request.

If successful, the Bluetooth driver stack can then notify the profile driver when remote devices
    attempt to create a SCO connection to the profile driver.

After the profile driver has registered itself, the Bluetooth driver stack can notify it when a remote
    device attempts to connect to it by calling the 
    <a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a> that the
    profile driver implements and specifies in the 
    <b>IndicationCallback</b> member.

When the profile driver receives notification of a connection attempt, it should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://social.msdn.microsoft.com/Forums/0a9a4323-d046-4d27-9d22-4974dbab30a4/windows-bluetooth-sco-brbscoopenchannelresponse?forum=wdk">
    BRB_SCO_OPEN_CHANNEL_RESPONSE</a> request to either accept or reject the connection attempt. For more
    information about accepting or rejecting SCO connection attempts, see the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536870">_BRB_SCO_OPEN_CHANNEL</a> structure.

After a connection is established, the profile driver can issue other BRBs to communicate with the
    remote device.

To stop receiving remote connection notifications, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536630">
    BRB_SCO_UNREGISTER_SERVER</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536628">BRB_SCO_REGISTER_SERVER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536630">BRB_SCO_UNREGISTER_SERVER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558678">ObReferenceObject</a>



<a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a>
 

 

