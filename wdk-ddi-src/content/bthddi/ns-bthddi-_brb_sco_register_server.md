---
UID: NS:bthddi._BRB_SCO_REGISTER_SERVER
title: _BRB_SCO_REGISTER_SERVER (bthddi.h)
description: A profile driver uses the _BRB_SCO_REGISTER_SERVER structure to register itself as a server capable of receiving SCO connections from remote Bluetooth devices.
old-location: bltooth\_brb_sco_register_server.htm
tech.root: bltooth
ms.assetid: c7d7a70d-f84b-4937-ac7b-297016d01d42
ms.date: 04/27/2018
ms.keywords: "_BRB_SCO_REGISTER_SERVER, _BRB_SCO_REGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_sco_register_server, bth_structs_332b94af-3e05-4adb-9e89-4933e119df51.xml, bthddi/_BRB_SCO_REGISTER_SERVER"
ms.topic: struct
f1_keywords:
 - "bthddi/_BRB_SCO_REGISTER_SERVER"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthddi.h
api_name:
- _BRB_SCO_REGISTER_SERVER
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a>, implemented
     by the profile driver, that the Bluetooth driver stack should call to notify the profile driver about
     incoming SCO connections.


### -field IndicationCallbackContext

The context passed to the function that is defined in the 
     <b>IndicationCallback</b> member.


### -field ReferenceObject

A pointer to an object to pass to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a> and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> functions to
     maintain a reference count of. Profile drivers should provide this object in such a way that the
     Bluetooth driver stack can increase the count of the object for as long as the driver stack can call the
     callback function specified in the 
     <b>IndicationCallback</b> member. The Bluetooth driver stack will decrease the reference count of the
     object when the profile driver 
     <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">builds and sends</a> a 
     <a href="https://docs.microsoft.com/previous-versions/ff536630(v=vs.85)">
     BRB_SCO_UNREGISTER_SERVER</a> request.


### -field ServerHandle

Handle to the SCO server, if successfully returned. When the profile driver should no longer
     receive remote connect indications it should pass this handle to 
     <a href="https://docs.microsoft.com/previous-versions/ff536630(v=vs.85)">
     BRB_SCO_UNREGISTER_SERVER</a>.


## -remarks



To register itself as a SCO server, a profile driver should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536628(v=vs.85)">BRB_SCO_REGISTER_SERVER</a> request.

If successful, the Bluetooth driver stack can then notify the profile driver when remote devices
    attempt to create a SCO connection to the profile driver.

After the profile driver has registered itself, the Bluetooth driver stack can notify it when a remote
    device attempts to connect to it by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a> that the
    profile driver implements and specifies in the 
    <b>IndicationCallback</b> member.

When the profile driver receives notification of a connection attempt, it should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://social.msdn.microsoft.com/Forums/0a9a4323-d046-4d27-9d22-4974dbab30a4/home?forum=windows-bluetooth-sco-brbscoopenchannelresponse">
    BRB_SCO_OPEN_CHANNEL_RESPONSE</a> request to either accept or reject the connection attempt. For more
    information about accepting or rejecting SCO connection attempts, see the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_open_channel">_BRB_SCO_OPEN_CHANNEL</a> structure.

After a connection is established, the profile driver can issue other BRBs to communicate with the
    remote device.

To stop receiving remote connection notifications, a profile driver should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536630(v=vs.85)">
    BRB_SCO_UNREGISTER_SERVER</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536628(v=vs.85)">BRB_SCO_REGISTER_SERVER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536630(v=vs.85)">BRB_SCO_UNREGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obfreferenceobject">ObReferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a>
 

 

