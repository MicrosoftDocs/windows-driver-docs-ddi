---
UID: NE:bthddi._BRB_TYPE
title: _BRB_TYPE (bthddi.h)
description: The BRB_TYPE enumeration type is used to determine the Bluetooth request block when a profile driver builds and sends a BRB.
old-location: bltooth\brb_type.htm
tech.root: bltooth
ms.assetid: 590e13cf-6cbc-4a7f-a68e-ada4a5027ed2
ms.date: 04/27/2018
ms.keywords: BRB_ACL_ENTER_ACTIVE_MODE, BRB_GET_DEVICE_INTERFACE_STRING, BRB_HCI_GET_LOCAL_BD_ADDR, BRB_L2CA_ACL_TRANSFER, BRB_L2CA_CLOSE_CHANNEL, BRB_L2CA_INFO_REQUEST, BRB_L2CA_OPEN_CHANNEL, BRB_L2CA_OPEN_CHANNEL_RESPONSE, BRB_L2CA_OPEN_ENHANCED_CHANNEL, BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE, BRB_L2CA_PING, BRB_L2CA_REGISTER_SERVER, BRB_L2CA_UNREGISTER_SERVER, BRB_L2CA_UPDATE_CHANNEL, BRB_REGISTER_PSM, BRB_SCO_CLOSE_CHANNEL, BRB_SCO_FLUSH_CHANNEL, BRB_SCO_GET_CHANNEL_INFO, BRB_SCO_GET_SYSTEM_INFO, BRB_SCO_OPEN_CHANNEL, BRB_SCO_OPEN_CHANNEL_RESPONSE, BRB_SCO_OPEN_UNMANAGED_CHANNEL, BRB_SCO_OPEN_UNMANAGED_CHANNEL_RESPONSE, BRB_SCO_REGISTER_SERVER, BRB_SCO_TRANSFER, BRB_SCO_UNREGISTER_SERVER, BRB_STORED_LINK_KEY, BRB_TYPE, BRB_TYPE enumeration [Bluetooth Devices], BRB_UNREGISTER_PSM, _BRB_TYPE, bltooth.brb_type, bth_enums_6d3541ca-7ba6-4430-9d97-55d88bea987f.xml, bthddi/BRB_ACL_ENTER_ACTIVE_MODE, bthddi/BRB_GET_DEVICE_INTERFACE_STRING, bthddi/BRB_HCI_GET_LOCAL_BD_ADDR, bthddi/BRB_L2CA_ACL_TRANSFER, bthddi/BRB_L2CA_CLOSE_CHANNEL, bthddi/BRB_L2CA_INFO_REQUEST, bthddi/BRB_L2CA_OPEN_CHANNEL, bthddi/BRB_L2CA_OPEN_CHANNEL_RESPONSE, bthddi/BRB_L2CA_OPEN_ENHANCED_CHANNEL, bthddi/BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE, bthddi/BRB_L2CA_PING, bthddi/BRB_L2CA_REGISTER_SERVER, bthddi/BRB_L2CA_UNREGISTER_SERVER, bthddi/BRB_L2CA_UPDATE_CHANNEL, bthddi/BRB_REGISTER_PSM, bthddi/BRB_SCO_CLOSE_CHANNEL, bthddi/BRB_SCO_FLUSH_CHANNEL, bthddi/BRB_SCO_GET_CHANNEL_INFO, bthddi/BRB_SCO_GET_SYSTEM_INFO, bthddi/BRB_SCO_OPEN_CHANNEL, bthddi/BRB_SCO_OPEN_CHANNEL_RESPONSE, bthddi/BRB_SCO_OPEN_UNMANAGED_CHANNEL, bthddi/BRB_SCO_OPEN_UNMANAGED_CHANNEL_RESPONSE, bthddi/BRB_SCO_REGISTER_SERVER, bthddi/BRB_SCO_TRANSFER, bthddi/BRB_SCO_UNREGISTER_SERVER, bthddi/BRB_STORED_LINK_KEY, bthddi/BRB_TYPE, bthddi/BRB_UNREGISTER_PSM
f1_keywords:
 - "bthddi/BRB_TYPE"
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
- BRB_TYPE
product:
- Windows
targetos: Windows
req.typenames: BRB_TYPE
---

# _BRB_TYPE enumeration


## -description


The <b>BRB_TYPE</b> enumeration type is used to determine the Bluetooth request block when a profile driver 
  <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">builds and sends</a> a BRB.


## -enum-fields




### -field BRB_HCI_GET_LOCAL_BD_ADDR

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_HCI_GET_LOCAL_BD_ADDR</b>.


### -field BRB_L2CA_REGISTER_SERVER

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_REGISTER_SERVER</b>.


### -field BRB_L2CA_UNREGISTER_SERVER

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_L2CA_UNREGISTER_SERVER</b>.


### -field BRB_L2CA_OPEN_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_OPEN_CHANNEL</b>.


### -field BRB_L2CA_OPEN_CHANNEL_RESPONSE

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b>.


### -field BRB_L2CA_CLOSE_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_CLOSE_CHANNEL</b>.


### -field BRB_L2CA_ACL_TRANSFER

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_ACL_TRANSFER</b>.


### -field BRB_L2CA_UPDATE_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_UPDATE_CHANNEL</b>.


### -field BRB_L2CA_PING

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_PING</b>.


### -field BRB_L2CA_INFO_REQUEST

For internal use only. Do not use.


### -field BRB_REGISTER_PSM

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_REGISTER_PSM</b>.


### -field BRB_UNREGISTER_PSM

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_UNREGISTER_PSM</b>.


### -field BRB_SCO_REGISTER_SERVER

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_REGISTER_SERVER</b>.


### -field BRB_SCO_UNREGISTER_SERVER

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_SCO_UNREGISTER_SERVER</b>.


### -field BRB_SCO_OPEN_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_OPEN_CHANNEL</b>.


### -field BRB_SCO_OPEN_CHANNEL_RESPONSE

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_SCO_OPEN_CHANNEL_RESPONSE</b>.


### -field BRB_SCO_CLOSE_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_CLOSE_CHANNEL</b>.


### -field BRB_SCO_TRANSFER

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_TRANSFER</b>.


### -field BRB_SCO_GET_CHANNEL_INFO

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_GET_CHANNEL_INFO</b>.


### -field BRB_SCO_GET_SYSTEM_INFO

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_GET_SYSTEM_INFO</b>.


### -field BRB_SCO_FLUSH_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_FLUSH_CHANNEL</b>.


### -field BRB_SCO_OPEN_UNMANAGED_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_SCO_OPEN_CHANNEL</b>.


### -field BRB_SCO_OPEN_UNMANAGED_CHANNEL_RESPONSE

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_SCO_OPEN_CHANNEL_RESPONSE</b>.


### -field BRB_L2CA_OPEN_ENHANCED_CHANNEL

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_OPEN_CHANNEL</b>. This value is present in Windows 8 and later versions of Windows.


### -field BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b>. This value is present in Windows 8 and later versions of Windows.


### -field BRB_ACL_GET_MODE


### -field BRB_ACL_ENTER_ACTIVE_MODE

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_ACL_ENTER_ACTIVE_MODE</b>.


### -field BRB_STORED_LINK_KEY

For internal use only. Do not use.


### -field BRB_GET_DEVICE_INTERFACE_STRING

This value declares a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a> of type 
     
     <b>BRB_GET_DEVICE_INTERFACE_STRING</b>.


## -remarks



The type of BRB is specified in the 
    <b>Type</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure. The 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_allocate_brb">BthAllocateBrb</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_initialize_brb">BthInitializeBrb</a> functions automatically
    set the 
    <b>Type</b> member.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb">BRB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_allocate_brb">BthAllocateBrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_initialize_brb">BthInitializeBrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_internal_bth_submit_brb">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>
 

 

