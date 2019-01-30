---
UID: NS:ks.__unnamed_struct_0
title: KSPRIORITY (ks.h)
description: The KSPRIORITY structure is used to specify priority and is used with the KSPROPERTY_CONNECTION_PRIORITY property.
old-location: stream\kspriority.htm
tech.root: stream
ms.assetid: 3bbef5f6-f859-4528-b044-baf8f99c2c2f
ms.date: 04/23/2018
ms.keywords: "*PKSPRIORITY, KSPRIORITY, KSPRIORITY structure [Streaming Media Devices], PKSPRIORITY, PKSPRIORITY structure pointer [Streaming Media Devices], ks-struct_08294311-6f72-4888-bfb8-b4598e1fc9bd.xml, ks/KSPRIORITY, ks/PKSPRIORITY, stream.kspriority"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSPRIORITY
product:
- Windows
targetos: Windows
req.typenames: KSPRIORITY, *PKSPRIORITY
---

# KSPRIORITY structure


## -description


The KSPRIORITY structure is used to specify priority and is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565104">KSPROPERTY_CONNECTION_PRIORITY</a> property.


## -struct-fields




### -field PriorityClass

Specifies a number ranging from 1 to 0xFFFFFFFF, where 1 is least priority and 0xFFFFFFFF is the highest priority. Zero is reserved for future use. When setting a class value, 0xFFFFFFFF is used to indicate exclusive access to the resources consumed by the pin. Possible values are listed in the following table.

<table>
<tr>
<th>PriorityClass</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPRIORITY_LOW

</td>
<td>
Specifies the lowest priority.

</td>
</tr>
<tr>
<td>
KSPRIORITY_NORMAL

</td>
<td>
Specifies normal priority.

</td>
</tr>
<tr>
<td>
KSPRIORITY_HIGH

</td>
<td>
Specifies an elevated priority.

</td>
</tr>
<tr>
<td>
KSPRIORITY_EXCLUSIVE

</td>
<td>
Specifies the highest priority, which implies exclusive access to resources.

</td>
</tr>
</table>
 


### -field PrioritySubClass

Specifies a number ranging from 1 to 0xFFFFFFFF, where 1 is the least priority within the class and 0xFFFFFFFF is the most priority. Zero is reserved for future use.


## -remarks



The KSPRIORITY.PrioritySubClass member allows a client to set exclusive use of resources consumed by a pin and also to prioritize the use of those resources by the client's pins within that exclusive class. The initial priority of a pin is set by the connection request typically performed through <a href="https://msdn.microsoft.com/library/windows/hardware/ff561652">KsCreatePin</a>, and is usually KSPRIORITY_NORMAL, with a subclass priority of 1. A pin uses these priorities as parameters when allocating shared resources from any component managing resources. Resource allocation occurs when formats are set on pins.

If the removal of resources by a higher priority client causes the filter pin to fail, the client must be notified through the KSEVENT_CONNECTION_PRIORITY event (assuming that the client had registered for event notification of this type).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565104">KSPROPERTY_CONNECTION_PRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561652">KsCreatePin</a>
 

 

