---
UID: NS:bthddi._CO_HEADER
title: _CO_HEADER (bthddi.h)
description: The CO_HEADER structure is used to specify values for the Header member of the L2CAP_CONFIG_OPTION structure.
old-location: bltooth\co_header.htm
tech.root: bltooth
ms.assetid: 76fa3316-bbec-4bf1-8cb8-d92e9f54d2d6
ms.date: 04/27/2018
keywords: ["_CO_HEADER structure"]
ms.keywords: CO_HEADER, CO_HEADER structure [Bluetooth Devices], _CO_HEADER, bltooth.co_header, bth_structs_bb345dd7-5895-472a-ab07-38c8b5ac6a72.xml, bthddi/CO_HEADER
f1_keywords:
 - "bthddi/CO_HEADER"
 - "CO_HEADER"
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
- CO_HEADER
product:
- Windows
targetos: Windows
req.typenames: CO_HEADER
---

# _CO_HEADER structure


## -description


The CO_HEADER structure is used to specify values for the 
  <b>Header</b> member of the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_l2cap_config_option">L2CAP_CONFIG_OPTION</a> structure.


## -struct-fields




### -field Type

The type of the vendor-specific option stored in the L2CAP_CONFIG_OPTION structure. This can
     accept either an option or a hint.


### -field Length

The size, in bytes, of the vendor-specific option stored in the L2CAP_CONFIG_OPTION
     structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_l2cap_config_option">L2CAP_CONFIG_OPTION</a>
 

 

