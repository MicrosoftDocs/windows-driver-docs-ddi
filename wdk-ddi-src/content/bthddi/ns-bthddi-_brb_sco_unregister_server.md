---
UID: NS:bthddi._BRB_SCO_UNREGISTER_SERVER
title: "_BRB_SCO_UNREGISTER_SERVER"
author: windows-driver-content
description: A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving SCO connections from remote Bluetooth devices.
old-location: bltooth\_brb_sco_unregister_server.htm
tech.root: bltooth
ms.assetid: a0624d6e-d3e9-45b1-b704-4a05532926f9
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "_BRB_SCO_UNREGISTER_SERVER, _BRB_SCO_UNREGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_sco_unregister_server, bth_structs_36fae461-b66e-42e0-8e66-a890e45abbbb.xml, bthddi/_BRB_SCO_UNREGISTER_SERVER"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_SCO_UNREGISTER_SERVER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_UNREGISTER_SERVER structure


## -description


A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving SCO connections from remote Bluetooth devices.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ServerHandle

The handle of the SCO server to unregister, that was obtained earlier from
     BRB_SCO_REGISTER_SERVER.


## -remarks



To unregister itself as a SCO server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536630">
    BRB_SCO_UNREGISTER_SERVER</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536630">BRB_SCO_UNREGISTER_SERVER</a>
 

 

