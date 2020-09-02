---
UID: NS:bthddi._BRB_GET_LOCAL_BD_ADDR
title: _BRB_GET_LOCAL_BD_ADDR (bthddi.h)
description: The _BRB_GET_LOCAL_BD_ADDR structure describes the address of the local radio.
old-location: bltooth\_brb_get_local_bd_addr.htm
tech.root: bltooth
ms.assetid: cddaa92c-c43b-4875-a52e-a28ecc30962d
ms.date: 04/27/2018
keywords: ["BRB_GET_LOCAL_BD_ADDR structure"]
ms.keywords: "_BRB_GET_LOCAL_BD_ADDR, _BRB_GET_LOCAL_BD_ADDR structure [Bluetooth Devices], bltooth._brb_get_local_bd_addr, bth_structs_eede3474-96b3-4865-a700-70f7e444a4c3.xml, bthddi/_BRB_GET_LOCAL_BD_ADDR"
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
targetos: Windows
req.typenames: 
f1_keywords:
 - _BRB_GET_LOCAL_BD_ADDR
 - bthddi/_BRB_GET_LOCAL_BD_ADDR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - _BRB_GET_LOCAL_BD_ADDR
---

# _BRB_GET_LOCAL_BD_ADDR structure


## -description

The _BRB_GET_LOCAL_BD_ADDR structure describes the address of the local radio.

## -struct-fields

### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

An output member that receives the address of the local radio.

## -remarks

To get the address of the local radio, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536611(v=vs.85)">
    BRB_HCI_GET_LOCAL_BD_ADDR</a> request.

Only a single local radio is supported by the Bluetooth driver stack.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff536611(v=vs.85)">BRB_HCI_GET_LOCAL_BD_ADDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>

