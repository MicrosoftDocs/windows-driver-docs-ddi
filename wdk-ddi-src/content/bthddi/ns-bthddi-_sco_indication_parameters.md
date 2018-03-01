---
UID: NS:bthddi._SCO_INDICATION_PARAMETERS
title: "_SCO_INDICATION_PARAMETERS"
author: windows-driver-content
description: The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification.
old-location: bltooth\sco_indication_parameters.htm
old-project: bltooth
ms.assetid: 2d3ae219-8a40-476c-b8eb-94f4c0566527
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS structure pointer [Bluetooth Devices], SCO_INDICATION_PARAMETERS, SCO_INDICATION_PARAMETERS structure [Bluetooth Devices], _SCO_INDICATION_PARAMETERS, bltooth.sco_indication_parameters, bth_structs_73ebf679-d092-4b0a-a54f-84539b8c85ae.xml, bthddi/PSCO_INDICATION_PARAMETERS, bthddi/SCO_INDICATION_PARAMETERS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	SCO_INDICATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: SCO_INDICATION_PARAMETERS, *PSCO_INDICATION_PARAMETERS
---

# _SCO_INDICATION_PARAMETERS structure


## -description


The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or
  disconnect notification.


## -syntax


````
typedef struct _SCO_INDICATION_PARAMETERS {
  SCO_CHANNEL_HANDLE ConnectionHandle;
  BTH_ADDR           BtAddress;
  union {
    struct {
      struct {
        SCO_LINK_TYPE LinkType;
      } Request;
    } Connect;
    struct {
      SCO_DISCONNECT_REASON Reason;
      BOOLEAN               CloseNow;
    } Disconnect;
  } Parameters;
} SCO_INDICATION_PARAMETERS, *PSCO_INDICATION_PARAMETERS;
````


## -struct-fields




### -field ConnectionHandle

A connection handle to the remote device. This handle is only valid for notifications that arrive
     over an established SCO connection.


### -field BtAddress

The Bluetooth address of the remote device.


### -field Parameters



#### 


### -field Parameters.Connect

The structure that contains parameters for the 
      <b>ScoIndicationRemoteConnectSCO_INDICATION_CODE</b> event.


### -field Parameters.Connect.Request

The structure that contains the parameters for the SCO connection request.



###### Connect.Request.LinkType

A value from the 
        <a href="..\bthddi\ne-bthddi-_sco_link_type.md">SCO_LINK_TYPE</a> enumeration that indicates the
        type of incoming connection.


### -field Parameters.Disconnect

The structure that contains parameters for the 
      <b>ScoIndicationRemoteDisconnectSCO_INDICATION_CODE</b> event.


### -field Parameters.Disconnect.Reason

A 
       <a href="..\bthddi\ne-bthddi-_sco_disconnect_reason.md">SCO_DISCONNECT_REASON</a> value that
       indicates why the SCO connection was terminated.


### -field Parameters.Disconnect.CloseNow

A Boolean value that a profile driver can set to indicate whether the SCO connection to the
       remote device will be closed. If the connection is to be closed, the value is <b>TRUE</b>. Otherwise, the
       value is <b>FALSE</b>.


## -remarks



A profile driver's 
    <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a> should process
    a notification differently depending upon the value that the Bluetooth driver stack passes in the 
    <i>Indication</i> parameter of the callback function.

When the Bluetooth driver stack passes 
    <b>ScoIndicationRemoteConnect</b>, the callback function should use the 
    <b>Connect</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>ScoIndicationRemoteDisconnect</b>, the callback function should use the 
    <b>Disconnect</b> member of the 
    <b>Parameters</b> union.




## -see-also

<a href="..\bthddi\ne-bthddi-_sco_disconnect_reason.md">SCO_DISCONNECT_REASON</a>



<a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SCO_INDICATION_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

