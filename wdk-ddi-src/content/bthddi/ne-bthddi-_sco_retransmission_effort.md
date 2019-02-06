---
UID: NE:bthddi._SCO_RETRANSMISSION_EFFORT
title: _SCO_RETRANSMISSION_EFFORT (bthddi.h)
description: The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a SCO channel.
old-location: bltooth\sco_retransmission_effort.htm
tech.root: bltooth
ms.assetid: bf466384-bf13-42cc-a02d-ef880cac4c02
ms.date: 04/27/2018
ms.keywords: "*PSCO_RETRANSMISSION_EFFORT, PSCO_RETRANSMISSION_EFFORT, PSCO_RETRANSMISSION_EFFORT enumeration pointer [Bluetooth Devices], SCO_RETRANSMISSION_DONT_CARE, SCO_RETRANSMISSION_EFFORT, SCO_RETRANSMISSION_EFFORT enumeration [Bluetooth Devices], SCO_RETRANSMISSION_MIN1_POWER, SCO_RETRANSMISSION_MIN1_QUALITY, SCO_RETRANSMISSION_NONE, _SCO_RETRANSMISSION_EFFORT, bltooth.sco_retransmission_effort, bth_enums_00709c56-9596-40d6-a789-840c5c1c7d33.xml, bthddi/PSCO_RETRANSMISSION_EFFORT, bthddi/SCO_RETRANSMISSION_DONT_CARE, bthddi/SCO_RETRANSMISSION_EFFORT, bthddi/SCO_RETRANSMISSION_MIN1_POWER, bthddi/SCO_RETRANSMISSION_MIN1_QUALITY, bthddi/SCO_RETRANSMISSION_NONE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	SCO_RETRANSMISSION_EFFORT
product:
- Windows
targetos: Windows
req.typenames: SCO_RETRANSMISSION_EFFORT, *PSCO_RETRANSMISSION_EFFORT
---

# _SCO_RETRANSMISSION_EFFORT enumeration


## -description


The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a
  SCO channel.


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

