---
UID: NS:bthddi._L2CAP_CONFIG_OPTION
title: "_L2CAP_CONFIG_OPTION"
author: windows-driver-content
description: An array of L2CAP_CONFIG_OPTION structures is used to specify values for the ExtraOptions member of the CHANNEL_CONFIG_PARAMETERS, _BRB_L2CA_OPEN_CHANNEL, and INDICATION_PARAMETERS structures.
old-location: bltooth\l2cap_config_option.htm
old-project: bltooth
ms.assetid: 9759c2b5-91c7-46e9-97dd-8268bf24db78
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PL2CAP_CONFIG_OPTION, L2CAP_CONFIG_OPTION, L2CAP_CONFIG_OPTION structure [Bluetooth Devices], PL2CAP_CONFIG_OPTION, PL2CAP_CONFIG_OPTION structure pointer [Bluetooth Devices], _L2CAP_CONFIG_OPTION, bltooth.l2cap_config_option, bth_structs_029f895f-fc15-4e53-9987-72f9930bc9ab.xml, bthddi/L2CAP_CONFIG_OPTION, bthddi/PL2CAP_CONFIG_OPTION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	L2CAP_CONFIG_OPTION
product: Windows
targetos: Windows
req.typenames: L2CAP_CONFIG_OPTION, *PL2CAP_CONFIG_OPTION
---

# _L2CAP_CONFIG_OPTION structure


## -description


An array of L2CAP_CONFIG_OPTION structures is used to specify values for the 
  <b>ExtraOptions</b> member of the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536659">CHANNEL_CONFIG_PARAMETERS</a>, 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a>, and 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a> structures.


## -struct-fields




### -field Header

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536673">CO_HEADER</a> structure that specifies information
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536659">CHANNEL_CONFIG_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20L2CAP_CONFIG_OPTION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

