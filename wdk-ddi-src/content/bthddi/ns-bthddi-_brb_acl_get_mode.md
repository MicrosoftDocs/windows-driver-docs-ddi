---
UID: NS:bthddi._BRB_ACL_GET_MODE
title: _BRB_ACL_GET_MODE (bthddi.h)
description: The _BRB_ACL_GET_MODE structure describes the ACL mode for the specified remote device.
old-location: bltooth\_brb_acl_get_mode.htm
tech.root: bltooth
ms.assetid: 2fe473c8-dcf9-4457-b1b1-c55b3eaa68e6
ms.date: 04/27/2018
keywords: ["_BRB_ACL_GET_MODE structure"]
ms.keywords: "_BRB_ACL_GET_MODE, _BRB_ACL_GET_MODE structure [Bluetooth Devices], bltooth._brb_acl_get_mode, bth_structs_ce659c96-d1af-4e27-b31a-f6700ff88331.xml, bthddi/_BRB_ACL_GET_MODE"
f1_keywords:
 - "bthddi/_BRB_ACL_GET_MODE"
 - "_BRB_ACL_GET_MODE"
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
- _BRB_ACL_GET_MODE
targetos: Windows
req.typenames: 
---

# _BRB_ACL_GET_MODE structure


## -description


The _BRB_ACL_GET_MODE structure describes the ACL mode for the specified remote device.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field AclMode

A value from the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_acl_mode">ACL_MODE</a> enumeration that specifies the ACL mode of
     the remote device.


## -remarks



To get the current ACL connection state for a remote device, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536609(v=vs.85)">BRB_ACL_GET_MODE</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_acl_mode">ACL_MODE</a>



<a href="https://docs.microsoft.com/previous-versions/ff536609(v=vs.85)">BRB_ACL_GET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>
 

 

