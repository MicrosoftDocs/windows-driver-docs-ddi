---
UID: NE:bthddi._SCO_RETRANSMISSION_EFFORT
title: "_SCO_RETRANSMISSION_EFFORT"
author: windows-driver-content
description: The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a SCO channel.
old-location: bltooth\sco_retransmission_effort.htm
old-project: bltooth
ms.assetid: bf466384-bf13-42cc-a02d-ef880cac4c02
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PSCO_RETRANSMISSION_EFFORT, ,, A, C, E, F, I, M, N, O, P, PSCO_RETRANSMISSION_EFFORT, PSCO_RETRANSMISSION_EFFORT enumeration pointer [Bluetooth Devices], R, S, SCO_RETRANSMISSION_DONT_CARE, SCO_RETRANSMISSION_EFFORT, SCO_RETRANSMISSION_EFFORT enumeration [Bluetooth Devices], SCO_RETRANSMISSION_MIN1_POWER, SCO_RETRANSMISSION_MIN1_QUALITY, SCO_RETRANSMISSION_NONE, T, _, _SCO_RETRANSMISSION_EFFORT, bltooth.sco_retransmission_effort, bth_enums_00709c56-9596-40d6-a789-840c5c1c7d33.xml, bthddi/PSCO_RETRANSMISSION_EFFORT, bthddi/SCO_RETRANSMISSION_DONT_CARE, bthddi/SCO_RETRANSMISSION_EFFORT, bthddi/SCO_RETRANSMISSION_MIN1_POWER, bthddi/SCO_RETRANSMISSION_MIN1_QUALITY, bthddi/SCO_RETRANSMISSION_NONE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	SCO_RETRANSMISSION_EFFORT
product: Windows
targetos: Windows
req.typenames: SCO_RETRANSMISSION_EFFORT, *PSCO_RETRANSMISSION_EFFORT
---

# _SCO_RETRANSMISSION_EFFORT enumeration


## -description


The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a
  SCO channel.


## -syntax


````
typedef enum _SCO_RETRANSMISSION_EFFORT { 
  SCO_RETRANSMISSION_NONE          = 0x00,
  SCO_RETRANSMISSION_MIN1_POWER    = 0x01,
  SCO_RETRANSMISSION_MIN1_QUALITY  = 0x02,
  SCO_RETRANSMISSION_DONT_CARE     = 0xFF
} SCO_RETRANSMISSION_EFFORT, *PSCO_RETRANSMISSION_EFFORT;
````


## -enum-fields




### -field SCO_RETRANSMISSION_NONE

The profile driver specifies that there should be no retransmissions on the channel.


### -field SCO_RETRANSMISSION_MIN1_POWER

The profile driver specifies that there should be at least one retransmission on the channel. Any
     retransmissions that are performed should be optimized for power consumption.


### -field SCO_RETRANSMISSION_MIN1_QUALITY

The profile driver specifies that there should be at least one retransmission on the channel. Any
     retransmissions that are performed should be optimized for link quality.


### -field SCO_RETRANSMISSION_DONT_CARE

The profile driver specifies that retransmissions can occur, but are not required.

