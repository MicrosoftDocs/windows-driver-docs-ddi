---
UID: NC:bthddi.PFNSCO_INDICATION_CALLBACK
title: PFNSCO_INDICATION_CALLBACK
author: windows-driver-content
description: Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any changes to the status of a currently open SCO connection.
old-location: bltooth\sco_callback_function.htm
old-project: bltooth
ms.assetid: abc9fc88-6852-4bfb-8271-7a73a508c397
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PFNSCO_INDICATION_CALLBACK, SCOIndicationCallback, SCOIndicationCallback callback function [Bluetooth Devices], bltooth.sco_callback_function, bth_funcs_05d035df-348d-42c0-8041-5d3822b0346e.xml, bthddi/SCOIndicationCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	bthddi.h
api_name:
-	SCOIndicationCallback
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# PFNSCO_INDICATION_CALLBACK callback


## -description


Profile drivers implement a SCO callback function to provide the Bluetooth driver stack with a
  mechanism to notify the profile driver about incoming SCO connection requests from remote devices, and any
  changes to the status of a currently open SCO connection.


## -prototype


````
PFNSCO_INDICATION_CALLBACK SCOIndicationCallback;

void SCOIndicationCallback(
  _In_ PVOID                      Context,
  _In_ SCO_INDICATION_CODE        Indication,
  _In_ PSCO_INDICATION_PARAMETERS Parameters
)
{ ... }
````


## -parameters




### -param Context [in]

For incoming remote connection request indications, this is the context specified by the profile
     driver in the 
     <b>IndicationCallbackContext</b> member of the 
     <a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a> structure
     when the profile driver registered the callback function. For changes to existing SCO connections, this
     is the 
     <b>CallbackContext</b> member specified by the profile driver when it built and sent a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a> BRB.


### -param Indication [in]

A 
     <a href="..\bthddi\ne-bthddi-_sco_indication_code.md">SCO_INDICATION_CODE</a> value that indicates
     the type of SCO event.


### -param Parameters [in]

A 
     <a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">
     SCO_INDICATION_PARAMETERS</a> structure that contains parameter information based on the value passed
     to the 
     <i>Indication</i> parameter.


## -returns



None




## -remarks



The 
    <b>BtAddress</b> member found in the SCO_INDICATION_PARAMETERS structure passed in the 
    <i>Parameters</i> parameter indicates the Bluetooth address of the remote device.

The 
    <i>PFNSCO_INDICATION_CALLBACK</i> function can be registered in two ways.

In the first case, the profile driver acts as a server and must register this callback function
    through the 
    <b>IndicationCallback</b> member of the 
    <a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a> structure.
    The Bluetooth driver stack can then call this function to notify the profile driver when a remote device
    attempts to contact it.

In the second case, the profile driver acts as a client and attempts to connect to a remote device
    using the <b>BRB_SCO_OPEN_CHANNEL</b> BRB. The 
    <i>PFNSCO_INDICATION_CALLBACK</i> callback function is registered through the 
    <b>Callback</b> member of the 
    <a href="..\bthddi\ns-bthddi-_brb_sco_open_channel.md">_BRB_SCO_OPEN_CHANNEL</a> structure passed
    with the specified BRB when one of them is submitted through 
    <a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">
    IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>.

After it is registered, the callback function is only associated with the channel that the BRB opened,
    and the function notifies the profile driver of actions that occur over the open channel to the remote
    device. Profile drivers can register a single function to handle channel notifications as a client and
    _BRB_SCO_REGISTER_SERVER notifications as a server.

The SCO_INDICATION_PARAMETERS structure held in the 
    <i>Parameters</i> parameter is interpreted according to the SCO_INDICATION_CODE value that is passed to
    the callback function through the 
    <i>Indication</i> parameter. For most notifications, there is a SCO_INDICATION_PARAMETERS union member
    that corresponds to the event and contains event-specific parameters.




## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a>



<a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">SCO_INDICATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a>



<a href="..\bthddi\ne-bthddi-_sco_indication_code.md">SCO_INDICATION_CODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PFNSCO_INDICATION_CALLBACK callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

