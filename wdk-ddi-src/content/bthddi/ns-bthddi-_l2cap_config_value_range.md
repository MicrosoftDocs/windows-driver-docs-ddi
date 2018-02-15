---
UID: NS:bthddi._L2CAP_CONFIG_VALUE_RANGE
title: "_L2CAP_CONFIG_VALUE_RANGE"
author: windows-driver-content
description: The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the Mtu and FlushTO members of the _BRB_L2CA_OPEN_CHANNEL structure.
old-location: bltooth\l2cap_config_value_range.htm
old-project: bltooth
ms.assetid: 12d9b0c1-6dce-4dc6-a8df-706408e1fbe1
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.l2cap_config_value_range, bthddi/L2CAP_CONFIG_VALUE_RANGE, bth_structs_3af526a5-d36e-432f-9d2e-fa31bee0effe.xml, L2CAP_CONFIG_VALUE_RANGE, bthddi/PL2CAP_CONFIG_VALUE_RANGE, PL2CAP_CONFIG_VALUE_RANGE structure pointer [Bluetooth Devices], _L2CAP_CONFIG_VALUE_RANGE, *PL2CAP_CONFIG_VALUE_RANGE, PL2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE structure [Bluetooth Devices]
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
-	L2CAP_CONFIG_VALUE_RANGE
product: Windows
targetos: Windows
req.typenames: "*PL2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE"
---

# _L2CAP_CONFIG_VALUE_RANGE structure


## -description


The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the 
  <b>Mtu</b> and 
  <b>FlushTO</b> members of the 
  <a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a> structure.


## -syntax


````
typedef struct _L2CAP_CONFIG_VALUE_RANGE {
  USHORT Min;
  USHORT Preferred;
  USHORT Max;
} L2CAP_CONFIG_VALUE_RANGE, *PL2CAP_CONFIG_VALUE_RANGE;
````


## -struct-fields




### -field Min

The minimum value that the local system will accept.


### -field Preferred

The ideal value that the local system requests that the remote device accept.


### -field Max

The maximum value that the local system will accept.


## -remarks



For 
    <b>FlushTO</b> member settings, the L2CAP_CONFIG_VALUE_RANGE structure contains the profile driver's ideal
    flush timeout value in the 
    <b>Preferred</b> member, along with a range of acceptable values as specified by the 
    <b>Min</b> and 
    <b>Max</b> members.

The profile driver uses a <b>BRB_L2CA_OPEN_CHANNEL</b> request to send these settings to a remote device with
    which it is attempting to create a L2CAP connection. If the 
    <b>Preferred</b> value that is sent by the profile driver falls in the range specified by the remote
    device, the 
    <b>FlushTO</b> settings are accepted. If the remote device rejects the setting as being too long, the
    remote device responds with the maximum setting it will accept. If the remote device's maximum flush
    timeout falls within the range defined by the 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> value is accepted. Otherwise, the remote device rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

If the remote device rejects the profile driver's 
    <b>Preferred</b> member value as being too short, the remote device responds with the minimum settings it
    will accept. If the remote device's minimum flush timeout falls within the range defined by the 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> value is accepted. Otherwise, the remote device rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

The profile driver negotiates these values separately from the flush timeout settings that it sends to
    the Bluetooth driver stack when a remote device attempts to create an inbound L2CAP channel to the
    profile driver. For more information about L2CAP configuration ranges, see 
    <a href="..\bthddi\ns-bthddi-_l2cap_config_range.md">L2CAP_CONFIG_RANGE</a>.

For 
    <b>Mtu</b> members settings, this structure provides 
    <b>Preferred</b>, 
    <b>Min</b>, and 
    <b>Max</b> settings for both inbound and outbound connections.




## -see-also

<a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20L2CAP_CONFIG_VALUE_RANGE structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

