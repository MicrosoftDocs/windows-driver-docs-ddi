---
UID: NE:bthddi._ACL_MODE
title: _ACL_MODE (bthddi.h)
description: The ACL_MODE enumeration type is used to list the possible states of an ACL connection.
old-location: bltooth\acl_mode.htm
tech.root: bltooth
ms.assetid: 90013f42-9393-4037-8d0d-13fe5d7caa0b
ms.date: 04/27/2018
ms.keywords: ACL_DISCONNECTED, ACL_MODE, ACL_MODE enumeration [Bluetooth Devices], ACL_MODE_ACTIVE, ACL_MODE_ENTER_ACTIVE, ACL_MODE_ENTER_HOLD, ACL_MODE_ENTER_PARK, ACL_MODE_ENTER_SNIFF, ACL_MODE_HOLD, ACL_MODE_PARK, ACL_MODE_SNIFF, _ACL_MODE, bltooth.acl_mode, bth_enums_52494ea2-66f0-4c7d-8f7b-c427a21ee826.xml, bthddi/ACL_DISCONNECTED, bthddi/ACL_MODE, bthddi/ACL_MODE_ACTIVE, bthddi/ACL_MODE_ENTER_ACTIVE, bthddi/ACL_MODE_ENTER_HOLD, bthddi/ACL_MODE_ENTER_PARK, bthddi/ACL_MODE_ENTER_SNIFF, bthddi/ACL_MODE_HOLD, bthddi/ACL_MODE_PARK, bthddi/ACL_MODE_SNIFF
ms.topic: enum
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
- ACL_MODE
product:
- Windows
targetos: Windows
req.typenames: ACL_MODE
---

# _ACL_MODE enumeration


## -description


The ACL_MODE enumeration type is used to list the possible states of an ACL connection.


## -enum-fields




### -field ACL_MODE_ACTIVE

This value indicates the ACL is in an active state.


### -field ACL_MODE_HOLD

This value indicates the ACL is in a hold state.


### -field ACL_MODE_SNIFF

This value indicates the ACL is in a sniffed state.


### -field ACL_MODE_PARK

This value indicates the ACL is in a parked state.


### -field ACL_MODE_ENTER_ACTIVE

This value indicates the ACL is entering an active state.


### -field ACL_MODE_ENTER_HOLD

This value indicates the ACL is entering a hold state.


### -field ACL_MODE_ENTER_SNIFF

This value indicates the ACL is entering a sniffed state.


### -field ACL_MODE_ENTER_PARK

This value indicates the ACL is entering a parked state.


### -field ACL_DISCONNECTED

This value indicates the ACL is disconnected.


## -remarks



The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536855">_BRB_ACL_GET_MODE</a> structure uses this
    enumeration.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536855">_BRB_ACL_GET_MODE</a>
 

 

