---
UID: NS:bthddi._CHANNEL_CONFIG_RESULTS
title: "_CHANNEL_CONFIG_RESULTS"
author: windows-driver-content
description: The CHANNEL_CONFIG_RESULTS structure contains configuration parameters and the buffer size of any extra options for the inbound and outbound directions of a L2CAP channel.
old-location: bltooth\channel_config_results.htm
old-project: bltooth
ms.assetid: cda3bfc6-7bdb-4b5a-8845-9a2ca1cc8014
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "*PCHANNEL_CONFIG_RESULTS, CHANNEL_CONFIG_RESULTS, CHANNEL_CONFIG_RESULTS structure [Bluetooth Devices], PCHANNEL_CONFIG_RESULTS, PCHANNEL_CONFIG_RESULTS structure pointer [Bluetooth Devices], _CHANNEL_CONFIG_RESULTS, bltooth.channel_config_results, bth_structs_9c4ea05f-7bee-473c-a311-e68f49c3013a.xml, bthddi/CHANNEL_CONFIG_RESULTS, bthddi/PCHANNEL_CONFIG_RESULTS"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	CHANNEL_CONFIG_RESULTS
product: Windows
targetos: Windows
req.typenames: CHANNEL_CONFIG_RESULTS, *PCHANNEL_CONFIG_RESULTS
---

# _CHANNEL_CONFIG_RESULTS structure


## -description


The CHANNEL_CONFIG_RESULTS structure contains configuration parameters and the buffer size of any
  extra options for the inbound and outbound directions of a L2CAP channel.


## -struct-fields




### -field Params

A 
     <a href="https://msdn.microsoft.com/c2201e3c-c680-4a22-adf5-5131fb138066">
     CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the specified direction of
     the channel.


### -field ExtraOptionsBufferSize

The size, in bytes, required in the buffer to retrieve the current extra options for the specified
     direction.


## -remarks



The CHANNEL_CONFIG_RESULTS structure is passed in the 
    <b>InResults</b> and 
    <b>OutResults</b> members of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536659">CHANNEL_CONFIG_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a>
 

 

