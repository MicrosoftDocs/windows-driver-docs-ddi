---
UID: NF:ks.KsProbeStreamIrp
title: KsProbeStreamIrp function
author: windows-driver-content
description: The KsProbeStreamIrp function makes the specified modifications to the input and output buffers of the given IRP based on the flags passed, and it then validates the stream header.
old-location: stream\ksprobestreamirp.htm
tech.root: stream
ms.assetid: 25b49781-2676-4b5e-b17b-dcb1bf98b297
ms.date: 4/23/2018
ms.keywords: KsProbeStreamIrp, KsProbeStreamIrp function [Streaming Media Devices], ks/KsProbeStreamIrp, ksfunc_0ed25e85-a785-4021-a7b7-59fa6230eff8.xml, stream.ksprobestreamirp
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsProbeStreamIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsProbeStreamIrp function


## -description


The <b>KsProbeStreamIrp</b> function makes the specified modifications to the input and output buffers of the given IRP based on the flags passed, and it then validates the stream header. This is useful when localizing exception handling or performing asynchronous work on an IRP. The resulting IRP is in essentially the METHOD_OUT_DIRECT or METHOD_IN_DIRECT format, with the exception that the access to the data buffer may be <b>IoModifyAccess</b>, depending on the flags passed to this function or the flags in the stream header. 


## -parameters




### -param Irp [in, out]

Specifies the IRP whose input and output buffers are to be mapped. The requester mode of the IRP is used when probing the buffers.


### -param ProbeFlags [in]

Specifies flags specifying how to probe the streaming IRP; the flags are listed in the following table.


### -param OPTIONAL






#### - HeaderSize [in, optional]

Specifies the size to validate each header header against passed to this client, or zero if no validation is to be done. If used, it is assumed that the entire buffer passed is a multiple of this header size, unless the buffer instead contains a single format change header.


## -returns



The <b>KsProbeStreamIrp</b> function returns STATUS_SUCCESS if successful, or it returns a memory or access error.




## -remarks



If the function is used only to allocate MDL's and not to probe and lock the addresses, the caller must have a completion routine to clean up the MDL's. For instance, a just-in-time locking mechanism can allocate the MDL list but only lock memory as needed. The client must provide cleanup code to remove the partially locked MDL list before the IRP is completed, presumably in a completion routine.

If the headers appear to have already been copied to a system buffer, it is not validated again. In general, calling the <b>KsProbeStreamIrp</b> function multiple times with an IRP is not harmful. After calling the function, the stream headers are available in PIRP.AssociatedIrp.SystemBuffer. If the stream buffer MDLs have been allocated, they are available through the PIRP.MdlAddress. 

The following defines are used for the <i>ProbeFlags</i> variable: 

<table>
<tr>
<th><i>ProbeFlags </i>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROBE_READ

</td>
<td>
Indicates that the operation is a stream read on the device. This is the default.

</td>
</tr>
<tr>
<td>
KSPROBE_WRITE

</td>
<td>
Indicates that the operation is a stream write on the device.

</td>
</tr>
<tr>
<td>
KSPROBE_ALLOCATEMDL

</td>
<td>
Indicates that MDLs should be allocated for the stream buffers if they have not already been allocated. If no stream buffers are present, the flag is ignored. If KSPROBE_PROBEANDLOCK is not specified at the same time as this flag, the caller must have a completion routine in order to clean up any MDL's if not all the MDLs were successfully probed and locked.

</td>
</tr>
<tr>
<td>
KSPROBE_PROBEANDLOCK

</td>
<td>
If the KSPROBE_ALLOCATEMDL is set, indicates that the memory referenced by the MDLs for the stream buffers should be probed and locked. If the MDL allocation flag is not set, this flag is ignored even if the MDL allocation has previously taken place. The method of probing is determined by what type of IRP is being passed. For a write operation, <b>IoReadAccess</b> is used. For a read operation, <b>IoWriteAccess</b> is used. If the client that sent the data is using the nonpaged pooll, appropriate MDLs are initialized rather than probing and locking.

</td>
</tr>
<tr>
<td>
KSPROBE_SYSTEMADDRESS

</td>
<td>
Retrieves a system address for each MDL in the chain so the caller does not need to do this in a separate step. This is ignored if the probe and lock flag is not set, even if the MDLs have previously been probed.

</td>
</tr>
<tr>
<td>
KSPROBE_ALLOWFORMATCHANGE

</td>
<td>
For a Stream Write, allows the KSSTREAM_HEADER_OPTIONSF_TYPECHANGED flag to be set in the stream header. This implies that the stream header is not of extended length, even if an extended header size was indicated. Also, there may only be one stream header contained in the IRP in this case. The buffer associated with this header contains the new data format. For system memory data streams, the buffer should not have been acquired from the negotiated allocator, as it is not part of the data stream.

</td>
</tr>
</table>
 



