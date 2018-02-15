---
UID: NS:bthddi._BRB_SCO_UNREGISTER_SERVER
title: "_BRB_SCO_UNREGISTER_SERVER"
author: windows-driver-content
description: A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server capable of receiving SCO connections from remote Bluetooth devices.
old-location: bltooth\_brb_sco_unregister_server.htm
old-project: bltooth
ms.assetid: a0624d6e-d3e9-45b1-b704-4a05532926f9
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_BRB_SCO_UNREGISTER_SERVER, _BRB_SCO_UNREGISTER_SERVER structure [Bluetooth Devices], bth_structs_36fae461-b66e-42e0-8e66-a890e45abbbb.xml, bthddi/_BRB_SCO_UNREGISTER_SERVER, bltooth._brb_sco_unregister_server"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	_BRB_SCO_UNREGISTER_SERVER
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_UNREGISTER_SERVER structure


## -description


A profile driver uses the _BRB_SCO_UNREGISTER_SERVER structure to unregister itself as a server
  capable of receiving SCO connections from remote Bluetooth devices.


## -syntax


````
struct _BRB_SCO_UNREGISTER_SERVER {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
  PVOID      ServerHandle;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ServerHandle

The handle of the SCO server to unregister, that was obtained earlier from
     BRB_SCO_REGISTER_SERVER.


## -remarks



To unregister itself as a SCO server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536630">
    BRB_SCO_UNREGISTER_SERVER</a> request.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536630">BRB_SCO_UNREGISTER_SERVER</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_UNREGISTER_SERVER structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

