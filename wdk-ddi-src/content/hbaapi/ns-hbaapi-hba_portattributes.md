---
UID: NS:hbaapi.HBA_PortAttributes
title: HBA_PortAttributes
description: The structure is used by the HBA_GetPortAttributesByWWN fibre channel HBA library routine to report the attributes for a specified remote fibre channel port.
old-location: storage\hba_portattributes.htm
tech.root: storage
ms.assetid: 7628c68b-b851-4b41-a86b-aa54e7cd6ddf
ms.date: 03/29/2018
ms.keywords: "*PHBA_PORTATTRIBUTES, HBA_PORTATTRIBUTES, HBA_PORTATTRIBUTES structure [Storage Devices], HBA_PortAttributes, HBA_PortAttributes structure [Storage Devices], PHBA_PORTATTRIBUTES, PHBA_PORTATTRIBUTES structure pointer [Storage Devices], hbaapi/HBA_PortAttributes, hbaapi/PHBA_PORTATTRIBUTES, storage.hba_portattributes, structs-Fibre_86dd88a9-06cc-4e24-a665-f4fa240795fb.xml"
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_PORTATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: HBA_PORTATTRIBUTES, *PHBA_PORTATTRIBUTES
---

# HBA_PortAttributes structure


## -description


The structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556104">HBA_GetPortAttributesByWWN</a> fibre channel HBA library routine to report the attributes for a specified remote fibre channel port.


## -struct-fields




### -field NodeWWN

Contains a 64 bit world-wide name (WWN) that uniquely identifies the fibre channel node associated with <b>PortWWN</b>. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field PortWWN

Contains a 64 bit world-wide name (WWN) that uniquely identifies the fibre channel port. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field PortFcId

Contains the current fibre channel address of <b>PortWWN</b>. The high order byte of this member contains the first byte of the address, and successively lower order bytes of this member contain successively lower bytes of the address. The lowest order byte of this member must be zero.


### -field PortType

Indicates the port type. This member must have one of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
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
Generic Fabric. 

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
 


### -field PortState

Contains the state of the port indicated by <b>PortWWN</b>. This member must have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
HBA_PORTSTATE_UNKNOWN

</td>
<td>
Unknown. 

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_ONLINE

</td>
<td>
Operational. 

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_OFFLINE

</td>
<td>
User Offline

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_BYPASSED

</td>
<td>
Bypassed. 

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_DIAGNOSTICS

</td>
<td>
In diagnostics mode.

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_LINKDOWN

</td>
<td>
Link Down

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_ERROR

</td>
<td>
Port Error. 

</td>
</tr>
<tr>
<td>
HBA_PORTSTATE_LOOPBACK

</td>
<td>
Loopback. 

</td>
</tr>
</table>
 


### -field PortSupportedClassofService

Indicates the class of service that are supported by <b>PortWWN</b>. For a list of the differences classes of service and the values that must be assigned to this member for each class, see the ANSI standard for <i>Fibre Channel Generic Services 4th Generation</i> (FC-GS-4).


### -field PortSupportedFc4Types

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556052">HBA_fc4types</a> that indicates the FC-4 types that are supported by <b>PortWWN</b>. For a discussion FC-4 types, see the ANSI standard for <i>Fibre Channel Generic Services 4th Generation</i> (FC-GS-4). 


### -field PortActiveFc4Types

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556052">HBA_fc4types</a> that indicates the FC-4 types that are currently available on <b>PortWWN</b>. For a discussion FC-4 types, see the ANSI standard for <i>Fibre Channel Generic Services 4th Generation</i> (FC-GS-4).


### -field PortSymbolicName

Contains the symbolic name of the port. 


### -field OSDeviceName


### -field PortSupportedSpeed

Indicates the signaling bit rates at which <b>PortWWN</b> can operate. For a list of the values that this member supports, see <b>PortSpeed</b>. 


### -field PortSpeed

Indicates the signaling bit rates at which <b>PortWWN</b> is currently operating. This member must have one of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
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
1 gigabit per sec

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_2GBIT

</td>
<td>
2 gigabits per sec

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_10GBIT

</td>
<td>
10 gigabits per sec

</td>
</tr>
<tr>
<td>
HBA_PORTSPEED_4GBIT

</td>
<td>
4 gigabits per sec

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
 


### -field PortMaxFrameSize

Indicates the maximum frame size, in bytes, that is supported by <b>PortWWN</b>.


### -field FabricName

Contains the name identifier for the fabric to which <b>PortWWN</b> is attached. 


### -field NumberofDiscoveredPorts

Indicates the number of ports that are visible to <b>PortWWN</b>. For a more detailed explanation of the sorts of ports that this number takes into consideration, see the T11 committee's specification for <i>Fibre Channel HBA API</i> (FC-HBA). 


## -remarks



The HBA_PortAttributes structure serves a purpose very similar to the MSFC_HBAPortAttributesResults structure that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a> WMI method to report port attributes.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556104">HBA_GetPortAttributesByWWN</a>
 

 

