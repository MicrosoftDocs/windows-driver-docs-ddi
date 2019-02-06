---
UID: NS:bthddi._BRB_ACL_ENTER_ACTIVE_MODE
title: _BRB_ACL_ENTER_ACTIVE_MODE (bthddi.h)
description: The _BRB_ACL_ENTER_ACTIVE_MODE structure specifies the remote device to be placed into active mode.
old-location: bltooth\_brb_acl_enter_active_mode.htm
tech.root: bltooth
ms.assetid: 2a42c8b5-acc0-463e-8ecd-179724be27d9
ms.date: 04/27/2018
ms.keywords: "_BRB_ACL_ENTER_ACTIVE_MODE, _BRB_ACL_ENTER_ACTIVE_MODE structure [Bluetooth Devices], bltooth._brb_acl_enter_active_mode, bth_structs_1cb3c3f5-063a-4213-98b0-5a2c667f5e40.xml, bthddi/_BRB_ACL_ENTER_ACTIVE_MODE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_ACL_ENTER_ACTIVE_MODE
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_ACL_ENTER_ACTIVE_MODE structure


## -description


The _BRB_ACL_ENTER_ACTIVE_MODE structure specifies the remote device to be placed into active
  mode.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


## -remarks



To place a remote device into active mode, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536854">
    BRB_ACL_ENTER_ACTIVE_MODE</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536854">BRB_ACL_ENTER_ACTIVE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>
 

 

