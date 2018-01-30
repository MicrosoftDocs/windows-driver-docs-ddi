---
UID: NS:bthddi._BRB_ACL_ENTER_ACTIVE_MODE
title: "_BRB_ACL_ENTER_ACTIVE_MODE"
author: windows-driver-content
description: The _BRB_ACL_ENTER_ACTIVE_MODE structure specifies the remote device to be placed into active mode.
old-location: bltooth\_brb_acl_enter_active_mode.htm
old-project: bltooth
ms.assetid: 2a42c8b5-acc0-463e-8ecd-179724be27d9
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_BRB_ACL_ENTER_ACTIVE_MODE, bth_structs_1cb3c3f5-063a-4213-98b0-5a2c667f5e40.xml, bltooth._brb_acl_enter_active_mode, bthddi/_BRB_ACL_ENTER_ACTIVE_MODE, _BRB_ACL_ENTER_ACTIVE_MODE structure [Bluetooth Devices]"
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
-	_BRB_ACL_ENTER_ACTIVE_MODE
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_ACL_ENTER_ACTIVE_MODE structure


## -description


The _BRB_ACL_ENTER_ACTIVE_MODE structure specifies the remote device to be placed into active
  mode.


## -syntax


````
struct _BRB_ACL_ENTER_ACTIVE_MODE {
  BRB_HEADER Hdr;
  BTH_ADDR   BtAddress;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


## -remarks


To place a remote device into active mode, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <mshelp:link keywords="bltooth.brb_acl_enter_active_mode" tabindex="0"><b>
    BRB_ACL_ENTER_ACTIVE_MODE</b></mshelp:link> request.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536854">BRB_ACL_ENTER_ACTIVE_MODE</a>

<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_ACL_ENTER_ACTIVE_MODE structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

