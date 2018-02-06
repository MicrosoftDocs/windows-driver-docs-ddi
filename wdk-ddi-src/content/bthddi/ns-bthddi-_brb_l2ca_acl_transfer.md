---
UID: NS:bthddi._BRB_L2CA_ACL_TRANSFER
title: "_BRB_L2CA_ACL_TRANSFER"
author: windows-driver-content
description: The _BRB_L2CA_ACL_TRANSFER structure describes a buffer to read asynchronous data from, or write asynchronous data to a L2CAP channel.
old-location: bltooth\_brb_l2ca_acl_transfer.htm
old-project: bltooth
ms.assetid: 8ab1365a-99bd-47b3-bf3d-8f70b4a7028a
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bthddi/_BRB_L2CA_ACL_TRANSFER, bltooth._brb_l2ca_acl_transfer, bth_structs_5dfd1186-d8a1-4ec5-9ce8-028d462fcb21.xml, _BRB_L2CA_ACL_TRANSFER, _BRB_L2CA_ACL_TRANSFER structure [Bluetooth Devices]
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
-	_BRB_L2CA_ACL_TRANSFER
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_ACL_TRANSFER structure


## -description


The _BRB_L2CA_ACL_TRANSFER structure describes a buffer to read asynchronous data from, or write
  asynchronous data to a L2CAP channel.


## -syntax


````
struct _BRB_L2CA_ACL_TRANSFER {
  BRB_HEADER           Hdr;
  BTH_ADDR             BtAddress;
  L2CAP_CHANNEL_HANDLE ChannelHandle;
  ULONG                TransferFlags;
  ULONG                BufferSize;
  PVOID                Buffer;
  PMDL                 BufferMDL;
  LONGLONG             Timeout;
  ULONG                RemainingBufferSize;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ChannelHandle

The L2CAP channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a> or 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
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
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536613">BRB_L2CA_ACL_TRANSFER</a> request.

Each L2CAP connection is bidirectional, and can be read from and written to simultaneously.

If no timeout is specified, BRBs associated with a read request will remain pending until data arrives
    or until they are canceled. Profile drivers can leave a read request pending in order to accept incoming
    data from the remote device.

The Bluetooth driver stack provides some buffering of incoming data, so it is not necessary to
    continuously check whether a read IRP is pending. A profile driver can specify the amount of buffering to
    provide in the 
    <b>IncomingQueueDepth</b> member associated with a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a> request.

If the ACL_TRANSFER_TIMEOUT flag is set in the 
    <b>TransferFlags</b> member and the duration specified in the 
    <b>Timeout</b> member expires, the <b>BRB_L2CA_ACL_TRANSFER</b> request will complete and return an error.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536613">BRB_L2CA_ACL_TRANSFER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a>

<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_ACL_TRANSFER structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

