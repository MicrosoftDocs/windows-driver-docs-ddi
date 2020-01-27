---
UID: NS:bthddi._BRB_SCO_GET_SYSTEM_INFO
title: _BRB_SCO_GET_SYSTEM_INFO (bthddi.h)
description: The _BRB_SCO_GET_SYSTEM_INFO structure describes information about the local system's support for SCO connections.
old-location: bltooth\_brb_sco_get_system_info.htm
tech.root: bltooth
ms.assetid: f8afda8b-12de-4955-8f25-0b2dae031ff1
ms.date: 04/27/2018
ms.keywords: "_BRB_SCO_GET_SYSTEM_INFO, _BRB_SCO_GET_SYSTEM_INFO structure [Bluetooth Devices], bltooth._brb_sco_get_system_info, bth_structs_970b0c43-701b-4219-b05c-aa49f8e6a09e.xml, bthddi/_BRB_SCO_GET_SYSTEM_INFO"
f1_keywords:
 - "bthddi/_BRB_SCO_GET_SYSTEM_INFO"
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
- _BRB_SCO_GET_SYSTEM_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_GET_SYSTEM_INFO structure


## -description


The _BRB_SCO_GET_SYSTEM_INFO structure describes information about the local system's support for SCO
  connections.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field Features

A flag or combination of flags that indicates what SCO features the system supports. Possible
     values include:
     


<dl>
<dt>SCO_FEATURE_ESCO_LINKS
     </dt>
<dt>SCO_FEATURE_SCO_LINKS</dt>
</dl>



### -field MaxChannels

The maximum number of active SCO channels that the system supports. This member is set to 0xFFFF
     if there is no limit or if the limit is unknown.


### -field TransferUnit

The minimum data transfer speed per each request, in milliseconds . Set to 0xFFFF if this value is
     variable or unknown.


### -field PacketTypes

A flag or combination of flags that indicates the type of SCO data packets that the local system
     supports. These SCO packet types are defined by the Bluetooth SIG. See the Bluetooth specification for
     more information about these flags. Possible values include:
     


<dl>
<dt>SCO_HV1
     </dt>
<dt>SCO_HV2
     </dt>
<dt>SCO_HV3
     </dt>
<dt>SCO_EV3
     </dt>
<dt>SCO_EV4
     </dt>
<dt>SCO_EV5</dt>
</dl>



### -field DataFormats

A flag or combination of flags the indicates the voice-encoding data formats supported by the
     local system. Possible values include:
     


<dl>
<dt>SCO_DATA_FORMAT_A_LAW_LOG 
     </dt>
<dt>SCO_DATA_FORMAT_CVSD
     </dt>
<dt>SCO_DATA_FORMAT_MU_LAW_LOG
     </dt>
<dt>SCO_DATA_FORMAT_TRANSPARENT</dt>
</dl>



### -field Reserved

Reserved for future use. Do not use.


## -remarks



To get the local system's support for SCO connections, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536625(v=vs.85)">BRB_SCO_GET_SYSTEM_INFO</a> request.

Higher-level profile drivers can build and send a <b>BRB_SCO_GET_SYSTEM_INFO</b> request to determine whether
    the local Bluetooth driver stack supports SCO connections, the maximum number of SCO channels that the
    system supports, and other useful information for opening a SCO connection to a remote device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536625(v=vs.85)">BRB_SCO_GET_SYSTEM_INFO</a>
 

 

