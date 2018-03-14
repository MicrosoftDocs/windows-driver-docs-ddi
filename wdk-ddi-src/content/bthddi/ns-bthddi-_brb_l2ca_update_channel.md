---
UID: NS:bthddi._BRB_L2CA_UPDATE_CHANNEL
title: "_BRB_L2CA_UPDATE_CHANNEL"
author: windows-driver-content
description: The _BRB_L2CA_UPDATE_CHANNEL structure describes an update to the link characteristics of an open L2CAP channel to a remote device or to ascertain when certain channel attributes have changed.
old-location: bltooth\_brb_l2ca_update_channel.htm
old-project: bltooth
ms.assetid: 0186dc75-6d37-4adb-8337-6daa634bd936
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_L2CA_UPDATE_CHANNEL, _BRB_L2CA_UPDATE_CHANNEL structure [Bluetooth Devices], bltooth._brb_l2ca_update_channel, bth_structs_7ee8d85e-5cf3-4820-a325-6abe0777b22a.xml, bthddi/_BRB_L2CA_UPDATE_CHANNEL"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_L2CA_UPDATE_CHANNEL
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_UPDATE_CHANNEL structure


## -description


The _BRB_L2CA_UPDATE_CHANNEL structure describes an update to the link characteristics of an open
  L2CAP channel to a remote device or to ascertain when certain channel attributes have changed.


## -syntax


````
struct _BRB_L2CA_UPDATE_CHANNEL {
  BRB_HEADER           Hdr;
  BTH_ADDR             BtAddress;
  L2CAP_CHANNEL_HANDLE ChannelHandle;
  ULONG                NewChannelFlags;
  ULONG                FailedChannelFlags;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The Bluetooth address of the remote device.


### -field ChannelHandle

The L2CAP channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a> or 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.


### -field NewChannelFlags


      A combination of flag values that specify the updated requirements for the channel. This member
      should be set to CF_ROLE_EITHER.
     


### -field FailedChannelFlags

The flag or flags in the 
     <b>NewChannelFlags</b> member that the Bluetooth driver stack was not able to honor. This member contains
     information only if the BRB call failed.


## -remarks



To retrieve the current settings of a L2CAP channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536620">BRB_L2CA_UPDATE_CHANNEL</a> request.

The profile driver can then determine when certain channel attributes have changed. Additionally, if
    the CF_LINK_PASSIVE_MODE flag is not set, the BRB will attempt to change the current channel settings to
    the remote device.

The primary use of <b>BRB_L2CA_UPDATE_CHANNEL</b> is to determine when authentication or encryption has been
    enabled for a connection.

In some cases, L2CAP connections can be established without the profile driver specifying that
    authentication is required, but authentication will happen automatically due to choices made by the user.
    In this case, a period of time passes between when the connection is established and when authentication
    and encryption begin working. Calls to <b>BRB_L2CA_UPDATE_CHANNEL</b> are blocked until authentication and
    encryption are complete.

By building and sending a <b>BRB_L2CA_UPDATE_CHANNEL</b> request, profile drivers can avoid using the
    connection prior to authentication.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536620">BRB_L2CA_UPDATE_CHANNEL</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_UPDATE_CHANNEL structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

