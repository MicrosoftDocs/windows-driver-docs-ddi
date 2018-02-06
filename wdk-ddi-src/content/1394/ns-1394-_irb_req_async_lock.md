---
UID: NS:1394._IRB_REQ_ASYNC_LOCK
title: "_IRB_REQ_ASYNC_LOCK"
author: windows-driver-content
description: This structure contains the fields necessary for the 1394 stack to carry out an asychronous lock request.
old-location: ieee\irb_req_async_lock.htm
old-project: IEEE
ms.assetid: 735C613E-BEAA-4E95-AF9D-A94A4BD940DE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IRB_REQ_ASYNC_LOCK structure [Buses], IRB_REQ_ASYNC_LOCK, IEEE.irb_req_async_lock, _IRB_REQ_ASYNC_LOCK, 1394/IRB_REQ_ASYNC_LOCK
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
-	IRB_REQ_ASYNC_LOCK
product: Windows
targetos: Windows
req.typenames: IRB_REQ_ASYNC_LOCK
---

# _IRB_REQ_ASYNC_LOCK structure


## -description


This structure contains the fields necessary for the 1394 stack to carry out an asychronous lock request.


## -syntax


````
typedef struct _IRB_REQ_ASYNC_LOCK {
  IO_ADDRESS DestinationAddress;
  ULONG      nNumberOfArgBytes;
  ULONG      nNumberOfDataBytes;
  ULONG      fulTransactionType;
  ULONG      fulFlags;
  ULONG      Arguments[2];
  ULONG      DataValues[2];
  PVOID      pBuffer;
  ULONG      ulGeneration;
  UCHAR      chPriority;
  UCHAR      nSpeed;
  UCHAR      tCode;
  UCHAR      Reserved;
} IRB_REQ_ASYNC_LOCK;
````


## -struct-fields




### -field DestinationAddress

Specifies the 1394 64-bit destination address for this read operation. The driver only needs to fill in the <b>IA_Destination_Offset</b> member of <b>u.AsyncLock.DestinationAddress</b>; the bus driver fills in the <b>IA_Destination_ID</b> member. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537346">IO_ADDRESS</a> for the structure description.


### -field nNumberOfArgBytes

Specifies the number of argument bytes used in performing this lock operation. May be zero, 4 or 8. See the <b>u.AsyncLock.fulTransactionType</b> member for details.


### -field nNumberOfDataBytes

Specifies the number of data bytes used in performing this lock operation. May be 4 or 8. See the <b>u.AsyncLock.fulTransactionType</b> member for details.


### -field fulTransactionType

Specifies which atomic transaction to execute on the 1394 node. The following function types are supported.
<table>
<tr>
<th>fulTransactionType</th>
<th>Description</th>
</tr>
<tr>
<td>
LOCK_TRANSACTION_MASK_SWAP

</td>
<td>
For each bit in the original value and the matching argument, reset the bit to be the same as the corresponding bit in the data value. The <b>nNumberOfArgBytes</b> and <b>nNumberOfDataBytes</b> members of <b>u.AsyncLock</b> must be the same.

</td>
</tr>
<tr>
<td>
LOCK_TRANSACTION_COMPARE_SWAP

</td>
<td>
If the original value and argument match, replace the original value with the data value. The <b>nNumberOfArgBytes</b> and <b>nNumberOfDataBytes</b> members of <b>u.AsyncLock</b> must be the same.

</td>
</tr>
<tr>
<td>
LOCK_TRANSACTION_FETCH_ADD

</td>
<td>
Add the data value to the original value. Big-endian addition is performed. The argument value is not used and the <b>nNumberOfArgBytes</b> member of <b>u.AsyncLock</b> must be zero.

</td>
</tr>
<tr>
<td>
LOCK_TRANSACTION_LITTLE_ADD

</td>
<td>
Add the data value to the original value. Little-endian addition is performed. The argument value is not used and the <b>nNumberOfArgBytes</b> member of <b>u.AsyncLock</b> must be zero.

</td>
</tr>
<tr>
<td>
LOCK_TRANSACTION_BOUNDED_ADD

</td>
<td>
If the original value and the argument differ, add the data value to the original value. The <b>nNumberOfArgBytes</b> and <b>nNumberOfDataBytes</b> members of <b>u.AsyncLock</b> must be the same.

</td>
</tr>
<tr>
<td>
LOCK_TRANSACTION_WRAP_ADD

</td>
<td>
If the original value and the argument differ, add the data value to original value. Otherwise, replace the original value with the data value. The <b>nNumberOfArgBytes</b> and <b>nNumberOfDataBytes</b> members of <b>u.AsyncLock</b> must be the same.

</td>
</tr>
</table> 


### -field fulFlags

Not currently used. Drivers should set this to zero.


### -field Arguments

Specifies the arguments used in this lock operation.


### -field DataValues

Specifies the data values used in this lock operation.


### -field pBuffer

Points to a buffer that receives lock data values returned from the node. The size of the buffer must be at least equal to the <b>u.AsyncLock.nNumberOfDataBytes</b> member.


### -field ulGeneration

Specifies the bus reset generation as known by the device driver who submitted this asynchronous request. If the generation count specified does not match the actual generation of the bus, then this request is returned with an error.


### -field chPriority

Reserved.


### -field nSpeed

Reserved.


### -field tCode

Reserved.


### -field Reserved

Reserved.

