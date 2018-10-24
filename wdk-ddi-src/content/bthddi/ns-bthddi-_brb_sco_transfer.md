---
UID: NS:bthddi._BRB_SCO_TRANSFER
title: "_BRB_SCO_TRANSFER"
author: windows-driver-content
description: The _BRB_SCO_TRANSFER structure describes a buffer to read isochronous data from, or write isochronous data to a SCO channel.
old-location: bltooth\_brb_sco_transfer.htm
tech.root: bltooth
ms.assetid: f0aeb4ad-17a6-43bb-87bf-0c6766a6ad39
ms.date: 04/27/2018
ms.keywords: "_BRB_SCO_TRANSFER, _BRB_SCO_TRANSFER structure [Bluetooth Devices], bltooth._brb_sco_transfer, bth_structs_2e4ed482-af73-4ca6-997c-53005c4fafc2.xml, bthddi/_BRB_SCO_TRANSFER"
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
-	_BRB_SCO_TRANSFER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_TRANSFER structure


## -description


The _BRB_SCO_TRANSFER structure describes a buffer to read isochronous data from, or write
  isochronous data to a SCO channel.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The Bluetooth address of the remote device.


### -field ChannelHandle

The SCO channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a> or 
     <a href="https://social.msdn.microsoft.com/Forums/0a9a4323-d046-4d27-9d22-4974dbab30a4/windows-bluetooth-sco-brbscoopenchannelresponse?forum=wdk">
     BRB_SCO_OPEN_CHANNEL_RESPONSE</a> request.


### -field TransferFlags

Flags that specify the basic behavior of the BRB. Valid flag values are listed in the following
     table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SCO_TRANSFER_DIRECTION_IN

</td>
<td>
If this bit is set, the BRB reads isochronous data from a remote device through the SCO
        channel.

</td>
</tr>
<tr>
<td>
SCO_TRANSFER_DIRECTION_OUT

</td>
<td>
If this bit is set, the BRB writes isochronousdata to a remote device through the SCO channel.

</td>
</tr>
</table>
 


### -field BufferSize

The size, in bytes, of the input buffer described by the 
     <b>Buffer</b> member of this structure.


### -field Buffer

A pointer to the input buffer. This value should be <b>NULL</b> when the 
     <b>Buffer</b> member is not used.


### -field BufferMDL

A pointer to the MDL input buffer. This value should be <b>NULL</b> when the 
     <b>BufferMDL</b> member is not used.


### -field DataTag



#### SCO write



#### 


## -remarks



To read isochronous data from or write isochronous data to a SCO connection, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536629">BRB_SCO_TRANSFER</a> request.

Each SCO connection is bidirectional, and can be read from and written to simultaneously.

Read BRBs will remain pending until data arrives or until the profile driver flushes them. It is
    recommended that higher-level drivers have at least two pending read BRBs open at any time to accept
    incoming data from the remote device.

The Bluetooth driver stack does not provide any buffering for incoming isochronous data. Therefore a
    small gap between the completion of one read IRP and the submission of the next can cause data loss.

If both 
    <b>Buffer</b> and 
    <b>BufferMDL</b> contain non-<b>NULL</b> values, then 
    <b>BufferMDL</b> takes precedence.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a>



<a href="https://social.msdn.microsoft.com/Forums/0a9a4323-d046-4d27-9d22-4974dbab30a4/windows-bluetooth-sco-brbscoopenchannelresponse?forum=wdk">BRB_SCO_OPEN_CHANNEL_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536629">BRB_SCO_TRANSFER</a>
 

 

