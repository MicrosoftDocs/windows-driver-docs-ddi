---
UID: NS:charging._CONFIGURABLE_CHARGER_PROPERTY_HEADER
title: _CONFIGURABLE_CHARGER_PROPERTY_HEADER (charging.h)
description: The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY.
old-location: battery\configurable_charger_property_header.htm
tech.root: battery
ms.assetid: 1A188828-51CE-4C80-92CB-2C01861082CD
ms.date: 02/15/2018
keywords: ["_CONFIGURABLE_CHARGER_PROPERTY_HEADER structure"]
ms.keywords: "*PCONFIGURABLE_CHARGER_PROPERTY_HEADER, CONFIGURABLE_CHARGER_PROPERTY_HEADER, CONFIGURABLE_CHARGER_PROPERTY_HEADER structure [Battery Devices], PCONFIGURABLE_CHARGER_PROPERTY_HEADER, PCONFIGURABLE_CHARGER_PROPERTY_HEADER structure pointer [Battery Devices], _CONFIGURABLE_CHARGER_PROPERTY_HEADER, battery.configurable_charger_property_header, charging/CONFIGURABLE_CHARGER_PROPERTY_HEADER, charging/PCONFIGURABLE_CHARGER_PROPERTY_HEADER"
f1_keywords:
 - "charging/CONFIGURABLE_CHARGER_PROPERTY_HEADER"
 - "CONFIGURABLE_CHARGER_PROPERTY_HEADER"
req.header: charging.h
req.include-header: Charging.h
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
- charging.h
api_name:
- CONFIGURABLE_CHARGER_PROPERTY_HEADER
product:
- Windows
targetos: Windows
req.typenames: CONFIGURABLE_CHARGER_PROPERTY_HEADER, *PCONFIGURABLE_CHARGER_PROPERTY_HEADER
---

# _CONFIGURABLE_CHARGER_PROPERTY_HEADER structure


## -description


The CONFIGURABLE_CHARGER_PROPERTY_HEADER structure is a header that is used to create your own structure as an input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/charging/ni-charging-ioctl_internal_configure_charger_property">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>.


## -struct-fields




### -field Size

Size of the structure.


### -field ChargerId

The charger ID.


### -field PropertyId

The ID of the property to be configured.


## -remarks



Extend this structure to add your own values for the input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/charging/ni-charging-ioctl_internal_configure_charger_property">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>. Create a new structure with <b>CONFIGURABLE_CHARGER_PROPERTY_HEADER</b> as the first field, and one or more values after it that correspond to your <b>PropertyId</b>. Here are two example structures.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct SET_MY_CHARGER_VOLTAGE {
    CONFIGURABLE_CHARGER_PROPERTY_HEADER Header;
    ULONG Voltage;
};</pre>
</td>
</tr>
</table></span></div>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>struct SET_MY_CHARGER_CURRENT_AND_VOLTAGE {
    CONFIGURABLE_CHARGER_PROPERTY_HEADER Header;
    ULONG Current;
    ULONG Voltage;
};</pre>
</td>
</tr>
</table></span></div>
Make sure you set <b>Header.Size</b> to the appropriate size of your new structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Header.Size = sizeof(SET_MY_CHARGER_VOLTAGE);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/charging/ni-charging-ioctl_internal_configure_charger_property">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>
 

 

