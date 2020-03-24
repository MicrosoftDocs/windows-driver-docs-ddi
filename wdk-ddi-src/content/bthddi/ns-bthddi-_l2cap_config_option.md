---
UID: NS:bthddi._L2CAP_CONFIG_OPTION
title: _L2CAP_CONFIG_OPTION (bthddi.h)
description: An array of L2CAP_CONFIG_OPTION structures is used to specify values for the ExtraOptions member of the CHANNEL_CONFIG_PARAMETERS, _BRB_L2CA_OPEN_CHANNEL, and INDICATION_PARAMETERS structures.
old-location: bltooth\l2cap_config_option.htm
tech.root: bltooth
ms.assetid: 9759c2b5-91c7-46e9-97dd-8268bf24db78
ms.date: 04/27/2018
keywords: ["_L2CAP_CONFIG_OPTION structure"]
ms.keywords: "*PL2CAP_CONFIG_OPTION, L2CAP_CONFIG_OPTION, L2CAP_CONFIG_OPTION structure [Bluetooth Devices], PL2CAP_CONFIG_OPTION, PL2CAP_CONFIG_OPTION structure pointer [Bluetooth Devices], _L2CAP_CONFIG_OPTION, bltooth.l2cap_config_option, bth_structs_029f895f-fc15-4e53-9987-72f9930bc9ab.xml, bthddi/L2CAP_CONFIG_OPTION, bthddi/PL2CAP_CONFIG_OPTION"
f1_keywords:
 - "bthddi/L2CAP_CONFIG_OPTION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthddi.h
api_name:
- L2CAP_CONFIG_OPTION
product:
- Windows
targetos: Windows
req.typenames: L2CAP_CONFIG_OPTION, *PL2CAP_CONFIG_OPTION
---

# _L2CAP_CONFIG_OPTION structure


## -description


An array of L2CAP_CONFIG_OPTION structures is used to specify values for the 
  <b>ExtraOptions</b> member of the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_channel_config_parameters">CHANNEL_CONFIG_PARAMETERS</a>, 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>, and 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a> structures.


## -struct-fields




### -field Header

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_co_header">CO_HEADER</a> structure that specifies information
     about vendor-specific configuration options.


### -field DynamicBuffer

A pointer to a buffer that contains additional L2CAP channel parameters that are defined either by
     the profile driver or the remote device. The 
     <b>Flags</b> member is set to CO_DYNAMIC to indicate that this member contains the extra
     parameters.


### -field FixedBuffer

A buffer that contains additional L2CAP channel parameters that are defined either by the profile
     driver or the remote device if they fit into 4 bytes. The 
     <b>Flags</b> member is set to CO_FIXED to indicate that this member contains the extra parameters.


### -field Flags

A combination of flags that determines which of this structure's buffer members contain
     parameters. Multiple flags can be set at once. Valid flag values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CO_DYNAMIC

</td>
<td>
If set, the 
        <b>DynamicBuffer</b> member points to the extra parameters.

</td>
</tr>
<tr>
<td>
CO_FIXED

</td>
<td>
If set, the 
        <b>FixedBuffer</b> member contains the extra parameters.

</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_channel_config_parameters">CHANNEL_CONFIG_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>
 

 

