---
UID: NS:1394._IRB_REQ_ASYNC_READ
title: "_IRB_REQ_ASYNC_READ"
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 stack to carry out an asynchronous read request.
old-location: ieee\irb_req_async_read.htm
old-project: IEEE
ms.assetid: C88A1F30-FC6B-4EC4-8F10-F507E17CF01D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "_IRB_REQ_ASYNC_READ, 1394/IRB_REQ_ASYNC_READ, IEEE.irb_req_async_read, IRB_REQ_ASYNC_READ, IRB_REQ_ASYNC_READ structure [Buses]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_ASYNC_READ
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ASYNC_READ
---

# _IRB_REQ_ASYNC_READ structure


## -description


This structure contains the fields necessary for the 1394 stack to carry out an asynchronous read request.


## -syntax


````
typedef struct _IRB_REQ_ASYNC_READ {
  IO_ADDRESS DestinationAddress;
  ULONG      nNumberOfBytesToRead;
  ULONG      nBlockSize;
  ULONG      fulFlags;
  PMDL       Mdl;
  ULONG      ulGeneration;
  UCHAR      chPriority;
  UCHAR      nSpeed;
  UCHAR      tCode;
  UCHAR      Reserved;
  ULONG      ElapsedTime;
} IRB_REQ_ASYNC_READ;
````


## -struct-fields




### -field DestinationAddress

Specifies the 1394 64-bit destination address for this read operation. The driver only needs to fill in the <b>IA_Destination_Offset</b> member of <b>DestinationAddress</b>; the bus driver fills in the <b>IA_Destination_ID</b> member. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537346">IO_ADDRESS</a> for the structure description.


### -field nNumberOfBytesToRead

Specifies the number of bytes to be read from the 1394 node.


### -field nBlockSize

Specifies the size of each individual block within the data stream that is read as a whole from the 1394 node. If this parameter is zero, the maximum packet size for the device and speed selected is used to issue these read requests, unless raw-mode addressing is used.



If raw-mode addressing is used, the client driver should set the <b>nBlockSize</b> member to the maximum asynchronous payload size that is supported by the device at the connected speed.



For more information on raw-mode addressing, see <a href="https://msdn.microsoft.com/93ad0cdf-5ac2-4916-b90e-1e64ca4494b6">Sending Asynchronous I/O Request Packets on the IEEE 1394 Bus.</a>
<div class="alert"><b>Note</b>  In Windows 7 and later versions of Windows, you can specify new values higher speed and  greater sized payloads. For more information, see <a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">New Flags for Speed and Payload Size</a> and <a href="https://msdn.microsoft.com/5473C6AC-284C-41B1-AA67-75696BE96C24">IEEE 1394 IOCTL Changes</a> in Device Driver Interface (DDI) Changes in Windows 7.</div>
<div> </div>



### -field fulFlags

Specifies any nondefault settings for this operation. The following flags are provided.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
 ASYNC_FLAGS_NONINCREMENTING

</td>
<td>
When the bus driver splits the request into blocks, begin the operation for each block at the same address, rather than treating each block as consecutive sections of the device's address space. Used only in asynchronous requests larger than <b>u.AsyncRead.nBlockSize</b> or the maximum packet size for the current speed.

</td>
</tr>
<tr>
<td>
ASYNC_FLAGS_PING

</td>
<td>
The bus driver returns the elapsed time of the operation in <b>u.AsyncRead.ElapsedTime</b>.

</td>
</tr>
</table>
 


### -field Mdl

Points to an MDL that describes the device driver's buffer, which receives data from the 1394 node.


### -field ulGeneration

Specifies the bus reset generation as known by the device driver that submits this asynchronous request. If the generation count specified does not match the actual generation of the bus, this request is returned with an error of STATUS_INVALID_GENERATION. 


### -field chPriority

Reserved. Drivers must set this to zero.


### -field nSpeed

Reserved. Drivers must set this to zero.


### -field tCode

Reserved. Drivers must set this to zero.


### -field Reserved

Reserved. Drivers must set this to zero.


### -field ElapsedTime

Elapsed time in nanoseconds. Only valid for flag ASYNC_FLAGS_PING.

