---
UID: NS:bthddi._CHANNEL_CONFIG_PARAMETERS
title: "_CHANNEL_CONFIG_PARAMETERS"
author: windows-driver-content
description: The CHANNEL_CONFIG_PARAMETERS structure contains configuration parameters for inbound and outbound directions of a L2CAP channel.
old-location: bltooth\channel_config_parameters.htm
old-project: bltooth
ms.assetid: c2201e3c-c680-4a22-adf5-5131fb138066
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PCHANNEL_CONFIG_PARAMETERS, ,, A, C, CHANNEL_CONFIG_PARAMETERS, CHANNEL_CONFIG_PARAMETERS structure [Bluetooth Devices], E, F, G, H, I, L, M, N, O, P, PCHANNEL_CONFIG_PARAMETERS, PCHANNEL_CONFIG_PARAMETERS structure pointer [Bluetooth Devices], R, S, T, _, _CHANNEL_CONFIG_PARAMETERS, bltooth.channel_config_parameters, bth_structs_c5360d7a-eb76-4b27-8507-8de862737a06.xml, bthddi/CHANNEL_CONFIG_PARAMETERS, bthddi/PCHANNEL_CONFIG_PARAMETERS"
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
-	CHANNEL_CONFIG_PARAMETERS
product: Windows
targetos: Windows
req.typenames: CHANNEL_CONFIG_PARAMETERS, *PCHANNEL_CONFIG_PARAMETERS
---

# _CHANNEL_CONFIG_PARAMETERS structure


## -description


The CHANNEL_CONFIG_PARAMETERS structure contains configuration parameters for inbound and outbound
  directions of a L2CAP channel.


## -syntax


````
typedef struct _CHANNEL_CONFIG_PARAMETERS {
  ULONG                Flags;
  CO_MTU               Mtu;
  CO_FLUSHTO           FlushTO;
  ULONG                NumExtraOptions;
  PL2CAP_CONFIG_OPTION ExtraOptions;
  L2CAP_FLOWSPEC       Flow;
} CHANNEL_CONFIG_PARAMETERS, *PCHANNEL_CONFIG_PARAMETERS;
````


## -struct-fields




### -field Flags

A flag or combination of flags that specifies which members of this structure contain data. Valid
     flag values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CFG_EXTRA

</td>
<td>
If set, the 
        <b>ExtraOptions</b> member contains data.

</td>
</tr>
<tr>
<td>
CFG_FLUSHTO

</td>
<td>
If set, the 
        <b>FlushTO</b> member contains data.

</td>
</tr>
<tr>
<td>
CFG_MTU

</td>
<td>
If set, the 
        <b>Mtu</b> member contains data.

</td>
</tr>
<tr>
<td>
CFG_QOS

</td>
<td>
If set, the 
        <b>Flow</b> member contains data.

</td>
</tr>
</table>
 


### -field Mtu

The message transfer units for the specified channel direction.


### -field FlushTO

The flush timeout for the specified channel direction.


### -field NumExtraOptions

The number of items specified in the array that is specified in the 
     <b>ExtraOptions</b> member.


### -field ExtraOptions

The number of items specified in the array that is specified in the 
     <b>ExtraOptions</b> member.


### -field Flow

The QoS settings for the specified channel direction.


## -see-also

<a href="..\bthddi\ns-bthddi-_l2cap_config_option.md">L2CAP_CONFIG_OPTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20CHANNEL_CONFIG_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

