---
UID: NS:bthddi._BRB_L2CA_UNREGISTER_SERVER
title: _BRB_L2CA_UNREGISTER_SERVER (bthddi.h)
description: A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving L2CAP connections from remote Bluetooth devices.
old-location: bltooth\_brb_l2ca_unregister_server.htm
tech.root: bltooth
ms.assetid: bc10d76f-da09-457a-b469-ef59d1cb09d9
ms.date: 04/27/2018
keywords: ["BRB_L2CA_UNREGISTER_SERVER structure"]
ms.keywords: "_BRB_L2CA_UNREGISTER_SERVER, _BRB_L2CA_UNREGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_l2ca_unregister_server, bth_structs_211f7f5f-0a2d-487e-9720-78076b36e012.xml, bthddi/_BRB_L2CA_UNREGISTER_SERVER"
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
 - _BRB_L2CA_UNREGISTER_SERVER
 - bthddi/_BRB_L2CA_UNREGISTER_SERVER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - _BRB_L2CA_UNREGISTER_SERVER
---

# _BRB_L2CA_UNREGISTER_SERVER structure


## -description

A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving L2CAP connections from remote Bluetooth devices.

## -struct-fields

### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.

### -field BtAddress

The address of the remote device.

### -field ServerHandle

The handle of the L2CAP server to unregister, as returned earlier from a previous 
     <a href="https://docs.microsoft.com/previous-versions/ff536618(v=vs.85)">
     BRB_L2CA_REGISTER_SERVER</a> request.

### -field Psm

The Protocol/Service Multiplexer (PSM) that was specified in a previous 
     <a href="https://docs.microsoft.com/previous-versions/ff536618(v=vs.85)">
     BRB_L2CA_REGISTER_SERVER</a> request.

## -remarks

To unregister itself as a L2CAP server, a profile driver should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">
    BRB_L2CA_UNREGISTER_SERVER</a> request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">BRB_L2CA_UNREGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">_BRB_L2CA_REGISTER_SERVER</a>

