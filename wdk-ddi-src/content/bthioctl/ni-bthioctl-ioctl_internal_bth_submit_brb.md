---
UID: NI:bthioctl.IOCTL_INTERNAL_BTH_SUBMIT_BRB
title: IOCTL_INTERNAL_BTH_SUBMIT_BRB (bthioctl.h)
description: Profile drivers use IOCTL_INTERNAL_BTH_SUBMIT_BRB to submit a Bluetooth Request Block (BRB) to the Bluetooth driver stack.
old-location: bltooth\ioctl_internal_bth_submit_brb.htm
tech.root: bltooth
ms.assetid: 60e4ee90-81d4-47a1-aed4-ee39b9fe3174
ms.date: 04/27/2018
keywords: ["IOCTL_INTERNAL_BTH_SUBMIT_BRB IOCTL"]
ms.keywords: IOCTL_INTERNAL_BTH_SUBMIT_BRB, IOCTL_INTERNAL_BTH_SUBMIT_BRB control, IOCTL_INTERNAL_BTH_SUBMIT_BRB control code [Bluetooth Devices], bltooth.ioctl_internal_bth_submit_brb, bth_ioctls_4b5e6ea0-3c6d-4453-9822-df845ebc2038.xml, bthioctl/IOCTL_INTERNAL_BTH_SUBMIT_BRB
req.header: bthioctl.h
req.include-header: BthIoctl.h
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_INTERNAL_BTH_SUBMIT_BRB
 - bthioctl/IOCTL_INTERNAL_BTH_SUBMIT_BRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - BthIoctl.h
api_name:
 - IOCTL_INTERNAL_BTH_SUBMIT_BRB
---

# IOCTL_INTERNAL_BTH_SUBMIT_BRB IOCTL


## -description

Profile drivers use <b>IOCTL_INTERNAL_BTH_SUBMIT_BRB</b> to submit a Bluetooth Request Block (BRB) to the
     Bluetooth driver stack.

## -ioctlparameters

### -input-buffer

The 
      <b>Parameters.Others.Argument1</b> member points to the address an instance of the
      structure that corresponds to the BRB that the profile driver intends to issue. The following list
      describes the structures that correspond to specific BRBs.

<table>
<tr>
<th>Bluetooth Request Block (BRB)</th>
<th>Corresponding structure</th>
</tr>
<tr>
<td>
BRB_HCI_GET_LOCAL_BD_ADDR

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_get_local_bd_addr">_BRB_GET_LOCAL_BD_ADDR</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_REGISTER_SERVER

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">_BRB_L2CA_REGISTER_SERVER</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_UNREGISTER_SERVER

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_unregister_server">
          _BRB_L2CA_UNREGISTER_SERVER</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_OPEN_CHANNEL

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_OPEN_CHANNEL_RESPONSE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_CLOSE_CHANNEL

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_close_channel">_BRB_L2CA_CLOSE_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_ACL_TRANSFER

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_acl_transfer">_BRB_L2CA_ACL_TRANSFER</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_UPDATE_CHANNEL

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_update_channel">_BRB_L2CA_UPDATE_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_L2CA_PING

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_ping">_BRB_L2CA_PING</a>


</td>
</tr>
<tr>
<td>
BRB_REGISTER_PSM

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_psm">_BRB_PSM</a>


</td>
</tr>
<tr>
<td>
BRB_UNREGISTER_PSM

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_psm">_BRB_PSM</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_REGISTER_SERVER

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_register_server">_BRB_SCO_REGISTER_SERVER</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_UNREGISTER_SERVER

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_unregister_server">_BRB_SCO_UNREGISTER_SERVER</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_OPEN_CHANNEL

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_open_channel">_BRB_SCO_OPEN_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_OPEN_CHANNEL_RESPONSE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_open_channel">_BRB_SCO_OPEN_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_CLOSE_CHANNEL

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_close_channel">_BRB_SCO_CLOSE_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_TRANSFER

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_transfer">_BRB_SCO_TRANSFER</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_GET_CHANNEL_INFO

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_get_channel_info">_BRB_SCO_GET_CHANNEL_INFO</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_GET_SYSTEM_INFO

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_get_system_info">_BRB_SCO_GET_SYSTEM_INFO</a>


</td>
</tr>
<tr>
<td>
BRB_SCO_FLUSH_CHANNEL

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_sco_flush_channel">_BRB_SCO_FLUSH_CHANNEL</a>


</td>
</tr>
<tr>
<td>
BRB_ACL_GET_MODE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_acl_get_mode">_BRB_ACL_GET_MODE</a>


</td>
</tr>
<tr>
<td>
BRB_ACL_ENTER_ACTIVE_MODE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_acl_enter_active_mode">_BRB_ACL_ENTER_ACTIVE_MODE</a>


</td>
</tr>
<tr>
<td>
BRB_GET_DEVICE_INTERFACE_STRING

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_get_device_interface_string">
          _BRB_GET_DEVICE_INTERFACE_STRING</a>


</td>
</tr>
</table>

### -input-buffer-length

The length of the structure.

### -output-buffer

If the BRB returns output, 
      <b>Parameters->Others.Argument1</b> points to the same BRB that was passed as input. Output is
      returned in the members of the associated BRB structure or in buffers that are specified in the BRB
      structure.

### -output-buffer-length

The length of the structure

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the 
      <b>Information</b> member of the <b>STATUS_BLOCK</b> structure is set to the size, in bytes, of the Bluetooth
      request block that was submitted. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_DEVICE_REQUEST

</td>
<td>
The request sent to the remote device through the BRB structure was invalid.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
One or more of the input parameters was invalid.

</td>
</tr>
<tr>
<td>

<dl>
<dt>STATUS_INVALID_BUFFER_SIZE or 
         </dt>
<dt>STATUS_BUFFER_TOO_SMALL</dt>
</dl>


</td>
<td>
The length of the supplied buffer was too small.

</td>
</tr>
<tr>
<td>
STATUS_NOT_IMPLEMENTED

</td>
<td>
The stack has not implemented the necessary module to process the BRB.

</td>
</tr>
<tr>
<td>
STATUS_NOT_SUPPORTED

</td>
<td>
The stack does not support this BRB.

</td>
</tr>
<tr>
<td>
STATUS_PENDING

</td>
<td>
The BRB is pending.

</td>
</tr>
</table>

## -remarks

Profile drivers use BRBs to handle most input, output, and connection tasks. A number of BRBs are
    defined for these tasks, and each one uses a specific, corresponding structure. All BRBs share a common
    header, which contains the type of the BRB. The Bluetooth driver stack uses the BRB header to correctly
    interpret the remainder of the BRB. For more information about BRB headers, see the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure.

For more information about how profile drivers use BRBs to communicate with the Bluetooth driver
    stack, see 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">Building and Sending a BRB</a>.

These BRBs must be called at IRQL <= PASSIVE_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_brb_type">BRB_TYPE</a>



<a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">Building and Sending a BRB</a>

