---
UID: NS:bthddi._BRB_L2CA_ACL_TRANSFER
title: _BRB_L2CA_ACL_TRANSFER (bthddi.h)
description: The _BRB_L2CA_ACL_TRANSFER structure describes a buffer to read asynchronous data from, or write asynchronous data to a L2CAP channel.
old-location: bltooth\_brb_l2ca_acl_transfer.htm
tech.root: bltooth
ms.assetid: 8ab1365a-99bd-47b3-bf3d-8f70b4a7028a
ms.date: 04/27/2018
keywords: ["_BRB_L2CA_ACL_TRANSFER structure"]
ms.keywords: "_BRB_L2CA_ACL_TRANSFER, _BRB_L2CA_ACL_TRANSFER structure [Bluetooth Devices], bltooth._brb_l2ca_acl_transfer, bth_structs_5dfd1186-d8a1-4ec5-9ce8-028d462fcb21.xml, bthddi/_BRB_L2CA_ACL_TRANSFER"
f1_keywords:
 - "bthddi/_BRB_L2CA_ACL_TRANSFER"
 - "_BRB_L2CA_ACL_TRANSFER"
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
- _BRB_L2CA_ACL_TRANSFER
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_ACL_TRANSFER structure


## -description


The _BRB_L2CA_ACL_TRANSFER structure describes a buffer to read asynchronous data from, or write
  asynchronous data to a L2CAP channel.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ChannelHandle

The L2CAP channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a> or 
     <a href="https://docs.microsoft.com/previous-versions/ff536616(v=vs.85)">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.


### -field TransferFlags

A combination of flags that specifies the basic behavior of the interface. Multiple flags can be
     set at the same time. Valid flag values are described in the following table:
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
ACL_SHORT_TRANSFER_OK

</td>
<td>
If this bit is set, the read operation can complete before the buffer is full. This can only be
        set in combination with ACL_TRANSFER_DIRECTION_IN.

</td>
</tr>
<tr>
<td>
ACL_TRANSFER_DIRECTION_IN

</td>
<td>
If this bit is set, data will be received from the remote device. This flag cannot be set in
        combination with ACL_TRANSFER_DIRECTION_OUT.

</td>
</tr>
<tr>
<td>
ACL_TRANSFER_DIRECTION_OUT

</td>
<td>
If this bit is set, data is to be sent to the remote device. This flag cannot be set in
        combination with ACL_TRANSFER_DIRECTION_IN.

</td>
</tr>
<tr>
<td>
ACL_TRANSFER_TIMEOUT

</td>
<td>
The read operation should be stopped after the number of milliseconds specified in the 
        <b>Timeout</b> member.

</td>
</tr>
</table>
 


### -field BufferSize

The size, in bytes, of the buffer.


### -field Buffer

A pointer to the input buffer.


### -field BufferMDL

A pointer to the MDL input buffer.


### -field Timeout

The duration, in milliseconds, before the read action is canceled and any data consumed to this
     point is lost.


### -field RemainingBufferSize

The amount of space, in bytes, left in the buffer after the BRB call.


## -remarks



To read asynchronous data from, or write asynchronous data to a L2CAP channel, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536613(v=vs.85)">BRB_L2CA_ACL_TRANSFER</a> request.

Each L2CAP connection is bidirectional, and can be read from and written to simultaneously.

If no timeout is specified, BRBs associated with a read request will remain pending until data arrives
    or until they are canceled. Profile drivers can leave a read request pending in order to accept incoming
    data from the remote device.

The Bluetooth driver stack provides some buffering of incoming data, so it is not necessary to
    continuously check whether a read IRP is pending. A profile driver can specify the amount of buffering to
    provide in the 
    <b>IncomingQueueDepth</b> member associated with a 
    <a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a> request.

If the ACL_TRANSFER_TIMEOUT flag is set in the 
    <b>TransferFlags</b> member and the duration specified in the 
    <b>Timeout</b> member expires, the <b>BRB_L2CA_ACL_TRANSFER</b> request will complete and return an error.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536613(v=vs.85)">BRB_L2CA_ACL_TRANSFER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a>



<a href="https://docs.microsoft.com/previous-versions/ff536616(v=vs.85)">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>
 

 

