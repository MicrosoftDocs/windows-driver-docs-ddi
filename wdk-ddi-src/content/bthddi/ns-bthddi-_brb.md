---
UID: NS:bthddi._BRB
title: _BRB (bthddi.h)
description: Profile drivers use Bluetooth request blocks (BRBs), to send requests to the Bluetooth driver stack. The BRB structure defines the format for all supported commands that can be sent to a Bluetooth device.
old-location: bltooth\brb.htm
tech.root: bltooth
ms.assetid: b9fc6eb9-6793-442a-a736-18929df14f20
ms.date: 04/27/2018
ms.keywords: "*PBRB, BRB, BRB structure [Bluetooth Devices], PBRB, PBRB structure pointer [Bluetooth Devices], _BRB, bltooth.brb, bth_structs_7ccc2ad1-dd10-4ae9-be41-fa79229b32aa.xml, bthddi/BRB, bthddi/PBRB"
ms.topic: struct
f1_keywords:
 - "bthddi/BRB"
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
- BRB
product:
- Windows
targetos: Windows
req.typenames: BRB, *PBRB
---

# _BRB structure


## -description


Profile drivers use Bluetooth request blocks (BRBs), to send requests to the Bluetooth driver stack.
  The BRB structure defines the format for all supported commands that can be sent to a Bluetooth
  device.


## -struct-fields




### -field BrbHeader

Describes basic information about the request being sent to the Bluetooth device. For more
      information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>.


### -field BrbGetDeviceInterfaceString

Defines the format for a command to get the interface string of the current Bluetooth device
      object. For more information about getting the device interface string, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_device_interface_string">
      _BRB_GET_DEVICE_INTERFACE_STRING</a>.


### -field BrbL2caRegisterServer

Defines the format for a command to register a L2CAP server. For more information about
      registering a L2CAP server, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_register_server">
      _BRB_L2CA_REGISTER_SERVER</a>.


### -field BrbL2caUnregisterServer

Defines the format for a command to unregister a previously registered L2CAP server. For more
      information about unregistering a L2CAP server, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_unregister_server">
      _BRB_L2CA_UNREGISTER_SERVER</a>.


### -field BrbL2caOpenChannel

Defines the format of the L2CAP open channel and the L2CAP open channel response commands sent to
      the Bluetooth device. For more information about opening a L2CAP channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>.


### -field BrbL2caCloseChannel

Defines the format of a L2CAP close channel command sent to the Bluetooth device. For more
      information about closing a L2CAP channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_close_channel">_BRB_L2CA_CLOSE_CHANNEL</a>.


### -field BrbL2caPing

Defines the format of a command that sends a L2CAP_EchoReq message to and receives a
      L2CAP_EchoRsp message from a remote Bluetooth device over a L2CAP connection. For more information
      about pinging a L2CAP connection, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_ping">_BRB_L2CA_PING</a>.


### -field BrbL2caAclTransfer

Defines the format of a command that performs read and write operations over a L2CAP connection
      to a Bluetooth device. For more information about ACL transfers, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_acl_transfer">_BRB_L2CA_ACL_TRANSFER</a>.


### -field BrbGetLocalBdAddress

Defines the format of a command that returns the address of the local Bluetooth radio. For more
      information about getting the local Bluetooth device address, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_local_bd_addr">_BRB_GET_LOCAL_BD_ADDR</a>.


### -field BrbPsm

Defines the format for the commands that register and unregister a Protocol/Service Multiplexer
      (PSM) that L2CAP Bluetooth devices connect to. For more information about PSMs, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_psm">_BRB_PSM</a>.


### -field BrbL2caUpdateChannel

Defines the format of a command that updates the settings of a L2CAP channel to a Bluetooth
      device. For more information about updating a L2CAP channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_update_channel">_BRB_L2CA_UPDATE_CHANNEL</a>.


### -field BrbScoRegisterServer

Defines the format for a command to register a SCO server. For more information about registering
      a SCO server, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_register_server">_BRB_SCO_REGISTER_SERVER</a>.


### -field BrbScoUnregisterServer

Defines the format for a command to unregister a previously registered SCO server. For more
      information about unregistering a SCO server, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_unregister_server">
      _BRB_SCO_UNREGISTER_SERVER</a>.


### -field BrbScoOpenChannel

Defines the format of SCO open channel and the SCO open channel response commands sent to the
      Bluetooth device. For more information about opening a SCO channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_open_channel">_BRB_SCO_OPEN_CHANNEL</a>.


### -field BrbScoCloseChannel

Defines the format of a SCO close channel command sent to the Bluetooth device. For more
      information about closing a SCO channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_close_channel">_BRB_SCO_CLOSE_CHANNEL</a>.


### -field BrbScoFlushChannel

Defines the format of a SCO flush channel command. For more information about flushing a SCO
      channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_flush_channel">_BRB_SCO_FLUSH_CHANNEL</a>.


### -field BrbScoTransfer

Defines the format of a command that reads isochronous data from or writes data to a SCO channel
      from a Bluetooth device. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_transfer">_BRB_SCO_TRANSFER</a>.


### -field BrbScoGetChannelInfo

Defines the format of a command that reads the settings of a SCO channel to a Bluetooth device.
      For more information about SCO transfers, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_get_channel_info">
      _BRB_SCO_GET_CHANNEL_INFO</a>.


### -field BrbScoGetSystemInfo

Defines the format of a command that reads the SCO settings of the local system. For more
      information about getting local SCO settings, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_get_system_info">_BRB_SCO_GET_SYSTEM_INFO</a>.


### -field BrbAclGetMode

Defines the format of a command to get the current ACL mode. For more information about getting
      the current ACL mode, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_acl_get_mode">_BRB_ACL_GET_MODE</a>.


### -field BrbAclEnterActiveMode

Defines the format of a command to enter active ACL mode. For more information about entering
      active ACL mode, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_acl_enter_active_mode">
      _BRB_ACL_ENTER_ACTIVE_MODE</a>.


### -field BrbL2caOpenEnhancedChannel

Defines the format of the enhanced L2CAP open channel and the enhanced L2CAP open channel response commands sent to
      the Bluetooth device. For more information about opening an enhanced L2CAP channel, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_open_enhanced_channel">_BRB_L2CA_OPEN_ENHANCED_CHANNEL</a>. This member is present in Windows 8 and later versions of Windows.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_acl_enter_active_mode">_BRB_ACL_ENTER_ACTIVE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_acl_get_mode">_BRB_ACL_GET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_device_interface_string">
   _BRB_GET_DEVICE_INTERFACE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_local_bd_addr">_BRB_GET_LOCAL_BD_ADDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_acl_transfer">_BRB_L2CA_ACL_TRANSFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_close_channel">_BRB_L2CA_CLOSE_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_ping">_BRB_L2CA_PING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_register_server">_BRB_L2CA_REGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_unregister_server">_BRB_L2CA_UNREGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_l2ca_update_channel">_BRB_L2CA_UPDATE_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_psm">_BRB_PSM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_close_channel">_BRB_SCO_CLOSE_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_flush_channel">_BRB_SCO_FLUSH_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_get_channel_info">_BRB_SCO_GET_CHANNEL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_get_system_info">_BRB_SCO_GET_SYSTEM_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_open_channel">_BRB_SCO_OPEN_CHANNEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_register_server">_BRB_SCO_REGISTER_SERVER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_transfer">_BRB_SCO_TRANSFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_sco_unregister_server">_BRB_SCO_UNREGISTER_SERVER</a>
 

 

