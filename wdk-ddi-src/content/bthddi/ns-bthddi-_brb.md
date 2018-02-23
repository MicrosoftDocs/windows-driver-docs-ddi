---
UID: NS:bthddi._BRB
title: "_BRB"
author: windows-driver-content
description: Profile drivers use Bluetooth request blocks (BRBs), to send requests to the Bluetooth driver stack. The BRB structure defines the format for all supported commands that can be sent to a Bluetooth device.
old-location: bltooth\brb.htm
old-project: bltooth
ms.assetid: b9fc6eb9-6793-442a-a736-18929df14f20
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PBRB, BRB structure [Bluetooth Devices], _BRB, bthddi/BRB, bltooth.brb, *PBRB, bth_structs_7ccc2ad1-dd10-4ae9-be41-fa79229b32aa.xml, BRB, PBRB structure pointer [Bluetooth Devices], bthddi/PBRB
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
-	BRB
product: Windows
targetos: Windows
req.typenames: BRB, *PBRB
---

# _BRB structure


## -description


Profile drivers use Bluetooth request blocks (BRBs), to send requests to the Bluetooth driver stack.
  The BRB structure defines the format for all supported commands that can be sent to a Bluetooth
  device.


## -syntax


````
typedef struct _BRB {
  union {
    struct _BRB_HEADER  BrbHeader;
    struct _BRB_GET_DEVICE_INTERFACE_STRING  BrbGetDeviceInterfaceString;
    struct _BRB_L2CA_REGISTER_SERVER  BrbL2caRegisterServer;
    struct _BRB_L2CA_UNREGISTER_SERVER  BrbL2caUnregisterServer;
    struct _BRB_L2CA_OPEN_CHANNEL  BrbL2caOpenChannel;
    struct _BRB_L2CA_CLOSE_CHANNEL  BrbL2caCloseChannel;
    struct _BRB_L2CA_PING  BrbL2caPing;
    struct _BRB_L2CA_ACL_TRANSFER  BrbL2caAclTransfer;
    struct _BRB_GET_LOCAL_BD_ADDR  BrbGetLocalBdAddress;
    struct _BRB_PSM  BrbPsm;
    struct _BRB_L2CA_UPDATE_CHANNEL  BrbL2caUpdateChannel;
    struct _BRB_SCO_REGISTER_SERVER  BrbScoRegisterServer;
    struct _BRB_SCO_UNREGISTER_SERVER  BrbScoUnregisterServer;
    struct _BRB_SCO_OPEN_CHANNEL  BrbScoOpenChannel;
    struct _BRB_SCO_CLOSE_CHANNEL  BrbScoCloseChannel;
    struct _BRB_SCO_FLUSH_CHANNEL  BrbScoFlushChannel;
    struct _BRB_SCO_TRANSFER  BrbScoTransfer;
    struct _BRB_SCO_GET_CHANNEL_INFO  BrbScoGetChannelInfo;
    struct _BRB_SCO_GET_SYSTEM_INFO  BrbScoGetSystemInfo;
    struct _BRB_ACL_GET_MODE  BrbAclGetMode;
    struct _BRB_ACL_ENTER_ACTIVE_MODE  BrbAclEnterActiveMode;
    struct _BRB_L2CA_OPEN_ENHANCED_CHANNEL  BrbL2caOpenEnhancedChannel;
  };
} BRB, *PBRB;
````


## -struct-fields






#### - BrbHeader

Describes basic information about the request being sent to the Bluetooth device. For more
      information, see 
      <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>.


#### - BrbGetDeviceInterfaceString

Defines the format for a command to get the interface string of the current Bluetooth device
      object. For more information about getting the device interface string, see 
      <a href="..\bthddi\ns-bthddi-_brb_get_device_interface_string.md">
      _BRB_GET_DEVICE_INTERFACE_STRING</a>.


#### - BrbL2caRegisterServer

Defines the format for a command to register a L2CAP server. For more information about
      registering a L2CAP server, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_register_server.md">
      _BRB_L2CA_REGISTER_SERVER</a>.


#### - BrbL2caUnregisterServer

Defines the format for a command to unregister a previously registered L2CAP server. For more
      information about unregistering a L2CAP server, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_unregister_server.md">
      _BRB_L2CA_UNREGISTER_SERVER</a>.


#### - BrbL2caOpenChannel

Defines the format of the L2CAP open channel and the L2CAP open channel response commands sent to
      the Bluetooth device. For more information about opening a L2CAP channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a>.


#### - BrbL2caCloseChannel

Defines the format of a L2CAP close channel command sent to the Bluetooth device. For more
      information about closing a L2CAP channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_close_channel.md">_BRB_L2CA_CLOSE_CHANNEL</a>.


#### - BrbL2caPing

Defines the format of a command that sends a L2CAP_EchoReq message to and receives a
      L2CAP_EchoRsp message from a remote Bluetooth device over a L2CAP connection. For more information
      about pinging a L2CAP connection, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_ping.md">_BRB_L2CA_PING</a>.


#### - BrbL2caAclTransfer

Defines the format of a command that performs read and write operations over a L2CAP connection
      to a Bluetooth device. For more information about ACL transfers, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_acl_transfer.md">_BRB_L2CA_ACL_TRANSFER</a>.


#### - BrbGetLocalBdAddress

Defines the format of a command that returns the address of the local Bluetooth radio. For more
      information about getting the local Bluetooth device address, see 
      <a href="..\bthddi\ns-bthddi-_brb_get_local_bd_addr.md">_BRB_GET_LOCAL_BD_ADDR</a>.


#### - BrbPsm

Defines the format for the commands that register and unregister a Protocol/Service Multiplexer
      (PSM) that L2CAP Bluetooth devices connect to. For more information about PSMs, see 
      <a href="..\bthddi\ns-bthddi-_brb_psm.md">_BRB_PSM</a>.


#### - BrbL2caUpdateChannel

Defines the format of a command that updates the settings of a L2CAP channel to a Bluetooth
      device. For more information about updaing a L2CAP channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_update_channel.md">_BRB_L2CA_UPDATE_CHANNEL</a>.


#### - BrbScoRegisterServer

Defines the format for a command to register a SCO server. For more information about registering
      a SCO server, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_register_server.md">_BRB_SCO_REGISTER_SERVER</a>.


#### - BrbScoUnregisterServer

Defines the format for a command to unregister a previously registered SCO server. For more
      information about unregistering a SCO server, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_unregister_server.md">
      _BRB_SCO_UNREGISTER_SERVER</a>.


#### - BrbScoOpenChannel

Defines the format of SCO open channel and the SCO open channel response commands sent to the
      Bluetooth device. For more information about opening a SCO channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_open_channel.md">_BRB_SCO_OPEN_CHANNEL</a>.


#### - BrbScoCloseChannel

Defines the format of a SCO close channel command sent to the Bluetooth device. For more
      information about closing a SCO channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_close_channel.md">_BRB_SCO_CLOSE_CHANNEL</a>.


#### - BrbScoFlushChannel

Defines the format of a SCO flush channel command. For more information about flushing a SCO
      channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_flush_channel.md">_BRB_SCO_FLUSH_CHANNEL</a>.


#### - BrbScoTransfer

Defines the format of a command that reads isochronous data from or writes data to a SCO channel
      from a Bluetooth device. For more information, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_transfer.md">_BRB_SCO_TRANSFER</a>.


#### - BrbScoGetChannelInfo

Defines the format of a command that reads the settings of a SCO channel to a Bluetooth device.
      For more information about SCO transfers, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_get_channel_info.md">
      _BRB_SCO_GET_CHANNEL_INFO</a>.


#### - BrbScoGetSystemInfo

Defines the format of a command that reads the SCO settings of the local system. For more
      information about getting local SCO settings, see 
      <a href="..\bthddi\ns-bthddi-_brb_sco_get_system_info.md">_BRB_SCO_GET_SYSTEM_INFO</a>.


#### - BrbAclGetMode

Defines the format of a command to get the current ACL mode. For more information about getting
      the current ACL mode, see 
      <a href="..\bthddi\ns-bthddi-_brb_acl_get_mode.md">_BRB_ACL_GET_MODE</a>.


#### - BrbAclEnterActiveMode

Defines the format of a command to enter active ACL mode. For more information about entering
      active ACL mode, see 
      <a href="..\bthddi\ns-bthddi-_brb_acl_enter_active_mode.md">
      _BRB_ACL_ENTER_ACTIVE_MODE</a>.


#### - BrbL2caOpenEnhancedChannel

Defines the format of the enhanced L2CAP open channel and the enhanced L2CAP open channel response commands sent to
      the Bluetooth device. For more information about opening an enhanced L2CAP channel, see 
      <a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_ENHANCED_CHANNEL</a>. This member is present in Windows 8 and later versions of Windows.


## -see-also

<a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_transfer.md">_BRB_SCO_TRANSFER</a>



<a href="..\bthddi\ns-bthddi-_brb_acl_get_mode.md">_BRB_ACL_GET_MODE</a>



<a href="..\bthddi\ns-bthddi-_brb_acl_enter_active_mode.md">_BRB_ACL_ENTER_ACTIVE_MODE</a>



<a href="..\bthddi\ns-bthddi-_brb_get_device_interface_string.md">
   _BRB_GET_DEVICE_INTERFACE_STRING</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_register_server.md">_BRB_L2CA_REGISTER_SERVER</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_flush_channel.md">_BRB_SCO_FLUSH_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_get_system_info.md">_BRB_SCO_GET_SYSTEM_INFO</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_close_channel.md">_BRB_L2CA_CLOSE_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_unregister_server.md">_BRB_L2CA_UNREGISTER_SERVER</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_acl_transfer.md">_BRB_L2CA_ACL_TRANSFER</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_close_channel.md">_BRB_SCO_CLOSE_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_get_local_bd_addr.md">_BRB_GET_LOCAL_BD_ADDR</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_ping.md">_BRB_L2CA_PING</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_unregister_server.md">_BRB_SCO_UNREGISTER_SERVER</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_update_channel.md">_BRB_L2CA_UPDATE_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_psm.md">_BRB_PSM</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_unregister_server.md">_BRB_L2CA_UNREGISTER_SERVER</a>



<a href="..\bthddi\ns-bthddi-_brb_sco_get_channel_info.md">_BRB_SCO_GET_CHANNEL_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BRB structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

