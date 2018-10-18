---
UID: NS:bthddi._BRB_L2CA_UNREGISTER_SERVER
title: "_BRB_L2CA_UNREGISTER_SERVER"
author: windows-driver-content
description: A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving L2CAP connections from remote Bluetooth devices.
old-location: bltooth\_brb_l2ca_unregister_server.htm
tech.root: bltooth
ms.assetid: bc10d76f-da09-457a-b469-ef59d1cb09d9
ms.date: 4/27/2018
ms.keywords: "_BRB_L2CA_UNREGISTER_SERVER, _BRB_L2CA_UNREGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_l2ca_unregister_server, bth_structs_211f7f5f-0a2d-487e-9720-78076b36e012.xml, bthddi/_BRB_L2CA_UNREGISTER_SERVER"
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
-	_BRB_L2CA_UNREGISTER_SERVER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_UNREGISTER_SERVER structure


## -description


A profile driver uses the _BRB_L2CA_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving L2CAP connections from remote Bluetooth devices.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ServerHandle

The handle of the L2CAP server to unregister, as returned earlier from a previous 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536618">
     BRB_L2CA_REGISTER_SERVER</a> request.


### -field Psm

The Protocol/Service Multiplexer (PSM) that was specified in a previous 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536618">
     BRB_L2CA_REGISTER_SERVER</a> request.


## -remarks



To unregister itself as a L2CAP server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">
    BRB_L2CA_UNREGISTER_SERVER</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">BRB_L2CA_UNREGISTER_SERVER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">_BRB_L2CA_REGISTER_SERVER</a>
 

 

