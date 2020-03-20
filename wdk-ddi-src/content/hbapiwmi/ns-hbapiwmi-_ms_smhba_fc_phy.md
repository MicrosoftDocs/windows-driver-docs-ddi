---
UID: NS:hbapiwmi._MS_SMHBA_FC_PHY
title: _MS_SMHBA_FC_PHY (hbapiwmi.h)
description: The MS_SMHBA_FC_PHY structure is used to report the physical attributes of a fibre channel port.
old-location: storage\ms_smhba_fc_phy.htm
tech.root: storage
ms.assetid: 7fb199b6-dcdb-41fc-b1c4-4eef2177018e
ms.date: 03/29/2018
keywords: ["_MS_SMHBA_FC_PHY structure"]
ms.keywords: "*PMS_SMHBA_FC_PHY, MS_SMHBA_FC_PHY, MS_SMHBA_FC_PHY structure [Storage Devices], PMS_SMHBA_FC_PHY, PMS_SMHBA_FC_PHY structure pointer [Storage Devices], _MS_SMHBA_FC_PHY, hbapiwmi/MS_SMHBA_FC_PHY, hbapiwmi/PMS_SMHBA_FC_PHY, storage.ms_smhba_fc_phy, structs-Fibre_64c8e970-8d72-4651-bcb8-8363b424cd04.xml"
f1_keywords:
 - "hbapiwmi/MS_SMHBA_FC_PHY"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- hbapiwmi.h
api_name:
- MS_SMHBA_FC_PHY
product:
- Windows
targetos: Windows
req.typenames: MS_SMHBA_FC_PHY, *PMS_SMHBA_FC_PHY
---

# _MS_SMHBA_FC_PHY structure


## -description


The MS_SMHBA_FC_PHY structure is used to report the physical attributes of a fibre channel port.


## -struct-fields




### -field PhySupportSpeed

The signaling bit rates at which the port can operate. For a list of the values that this member supports, see PhySpeed.


### -field PhySpeed

The signaling bit rates at which PortWWN is currently operating. This member must have one of the values in the following table.

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Meaning</b>

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_UNKNOWN

</td>
<td>
Speed unknown. The transceiver is incapable of reporting the speed. 

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_1GBIT

</td>
<td>
1 gigabit per sec.

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_2GBIT

</td>
<td>
2 gigabits per sec.

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_10GBIT

</td>
<td>
10 gigabits per sec.

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_4GBIT

</td>
<td>
4 gigabits per sec.

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_NOT_NEGOTIATED

</td>
<td>
The speed at which the port will operate has not yet been established. 

</td>
</tr>
</table>
 


### -field PhyType

The port type. This member must have one of the values in the following table.

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Meaning</b>

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_UNKNOWN

</td>
<td>
Unknown port type. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_OTHER

</td>
<td>
Value that is not a port type. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_NOTPRESENT

</td>
<td>
Port not present.

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_NPORT

</td>
<td>
Fabric. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_NLPORT

</td>
<td>
Public loop.

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_FLPORT

</td>
<td>
Fabric on a loop. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_FPORT

</td>
<td>
Fabric port. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_EPORT

</td>
<td>
Fabric expansion port. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_GPORT

</td>
<td>
Generic fabric. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_LPORT

</td>
<td>
Private loop port. 

</td>
</tr>
<tr>
<td>
HBA_PORTTYPE_PTP

</td>
<td>
Point to point. 

</td>
</tr>
</table>
 


### -field MaxFrameSize

The maximum frame size, in bytes, that is supported by PortWWN.

