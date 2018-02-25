---
UID: NS:bthddi._CHANNEL_CONFIG_RESULTS
title: "_CHANNEL_CONFIG_RESULTS"
author: windows-driver-content
description: The CHANNEL_CONFIG_RESULTS structure contains configuration parameters and the buffer size of any extra options for the inbound and outbound directions of a L2CAP channel.
old-location: bltooth\channel_config_results.htm
old-project: bltooth
ms.assetid: cda3bfc6-7bdb-4b5a-8845-9a2ca1cc8014
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PCHANNEL_CONFIG_RESULTS, ,, A, C, CHANNEL_CONFIG_RESULTS, CHANNEL_CONFIG_RESULTS structure [Bluetooth Devices], E, F, G, H, I, L, N, O, P, PCHANNEL_CONFIG_RESULTS, PCHANNEL_CONFIG_RESULTS structure pointer [Bluetooth Devices], R, S, T, U, _, _CHANNEL_CONFIG_RESULTS, bltooth.channel_config_results, bth_structs_9c4ea05f-7bee-473c-a311-e68f49c3013a.xml, bthddi/CHANNEL_CONFIG_RESULTS, bthddi/PCHANNEL_CONFIG_RESULTS"
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
-	CHANNEL_CONFIG_RESULTS
product: Windows
targetos: Windows
req.typenames: CHANNEL_CONFIG_RESULTS, *PCHANNEL_CONFIG_RESULTS
---

# _CHANNEL_CONFIG_RESULTS structure


## -description


The CHANNEL_CONFIG_RESULTS structure contains configuration parameters and the buffer size of any
  extra options for the inbound and outbound directions of a L2CAP channel.


## -syntax


````
typedef struct _CHANNEL_CONFIG_RESULTS {
  CHANNEL_CONFIG_PARAMETERS Params;
  ULONG                     ExtraOptionsBufferSize;
} CHANNEL_CONFIG_RESULTS, *PCHANNEL_CONFIG_RESULTS;
````


## -struct-fields




### -field Params

A 
     <a href="..\bthddi\ns-bthddi-_channel_config_parameters.md">
     CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the specified direction of
     the channel.


### -field ExtraOptionsBufferSize

The size, in bytes, required in the buffer to retrieve the current extra options for the specified
     direction.


## -remarks



The CHANNEL_CONFIG_RESULTS structure is passed in the 
    <b>InResults</b> and 
    <b>OutResults</b> members of the 
    <a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a> structure.




## -see-also

<a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_channel_config_parameters.md">CHANNEL_CONFIG_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20CHANNEL_CONFIG_RESULTS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

