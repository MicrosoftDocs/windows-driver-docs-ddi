---
UID: NS:ntifs._NETWORK_OPEN_ECP_CONTEXT
title: _NETWORK_OPEN_ECP_CONTEXT (ntifs.h)
description: The NETWORK_OPEN_ECP_CONTEXT structure is used to interpret network ECP contexts on files.
old-location: ifsk\network_open_ecp_context.htm
tech.root: ifsk
ms.assetid: 583fe92d-ce81-47b4-bd75-5566a5379790
ms.date: 04/16/2018
ms.keywords: "*PNETWORK_OPEN_ECP_CONTEXT, ECP_Structures_9cdb7dab-17df-47f3-b994-fca989b3442e.xml, NETWORK_OPEN_ECP_CONTEXT, NETWORK_OPEN_ECP_CONTEXT structure [Installable File System Drivers], PNETWORK_OPEN_ECP_CONTEXT, PNETWORK_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], _NETWORK_OPEN_ECP_CONTEXT, ifsk.network_open_ecp_context, ntifs/NETWORK_OPEN_ECP_CONTEXT, ntifs/PNETWORK_OPEN_ECP_CONTEXT"
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
- ntifs.h
api_name:
- NETWORK_OPEN_ECP_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: NETWORK_OPEN_ECP_CONTEXT, *PNETWORK_OPEN_ECP_CONTEXT
---

# _NETWORK_OPEN_ECP_CONTEXT structure


## -description


The <b>NETWORK_OPEN_ECP_CONTEXT</b> structure is used to interpret network ECP contexts on files. 


## -struct-fields




### -field Size

The size, in bytes, of this structure. 


### -field Reserved

Reserved. Must be set to zero. 


### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.in

 


### -field DUMMYSTRUCTNAME.in.Location

 


### -field DUMMYSTRUCTNAME.in.Integrity

 


### -field DUMMYSTRUCTNAME.in.Flags

 


### -field DUMMYSTRUCTNAME.out

 


### -field DUMMYSTRUCTNAME.out.Location

 


### -field DUMMYSTRUCTNAME.out.Integrity

 


### -field DUMMYSTRUCTNAME.out.Flags

 




#### - ( unnamed struct )

A structure that contains restrictions for opening the file and to apply to the file after it is opened. 



#### in

A structure in the DUMMYSTRUCTNAME structure that contains restrictions for opening a file.





##### Location

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550908">NETWORK_OPEN_LOCATION_QUALIFIER</a>-typed value that specifies the location restriction to attach to the file. 



##### Integrity

This member is currently not implemented and should be ignored. 

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550902">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>-typed value that specifies the integrity restriction to attach to the file. 



##### Flags

Supported starting with Windows 7.

A value that specifies attributes for the file. This member is a bitwise OR of any of the flags in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_COLLAPSING

(0x1)

</td>
<td>
This flag indicates to the SMB or SMB2 redirector that the incoming open request must not be piggybacked and collapsed onto an existing open handle to the same file.

</td>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_DURABILITY

(0x2)

</td>
<td>
This flag causes the SMB2 redirector to disable durability on this open handle. For more information about opening a file for durable operation, see <a href="https://go.microsoft.com/fwlink/p/?linkid=160861">Application Requests Creating a File Opened for Durable Operation</a>.

</td>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_DISABLE_OPLOCKS

(0x4)

</td>
<td>
This flag indicates to the SMB or SMB2 redirector not to grant oplocks for the  incoming open request.

This flag is available starting with Windows 8.

</td>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_FORCE_BUFFERED_SYNCHRONOUS_IO_HACK 

(0x80000000)

</td>
<td>
This flag is reserved for internal use and must not be used by applications.

This flag forces the redirector to use synchronous I/O even though the handle was opened for asynchronous I/O.

</td>
</tr>
</table>
 



#### out

A structure in the DUMMYSTRUCTNAME structure that contains information that a file provides after it is opened.





##### Location

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550908">NETWORK_OPEN_LOCATION_QUALIFIER</a>-typed value that specifies the location restriction to attach to the file. 



##### Integrity

This member is currently not implemented and should be ignored. 

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff550902">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>-typed value that specifies the integrity restriction to attach to the file. 



##### Flags

Supported starting with Windows 7.

A value that specifies attributes for the file. This member is a bitwise OR of any of the flags in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_COLLAPSING 

(0x1)

</td>
<td>
This flag indicates to the SMB or SMB2 redirector that the incoming open request must not be piggybacked and collapsed onto an existing open handle to the same file.

</td>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_DISABLE_HANDLE_DURABILITY 

(0x2)

</td>
<td>
This flag causes the SMB2 redirector to disable durability on this open handle. For more information about opening a file for durable operation, see <a href="https://go.microsoft.com/fwlink/p/?linkid=160861">Application Requests Creating a File Opened for Durable Operation</a>.

</td>
</tr>
<tr>
<td>
NETWORK_OPEN_ECP_IN_FLAG_FORCE_BUFFERED_SYNCHRONOUS_IO_HACK 

(0x80000000)

</td>
<td>
This flag is reserved for internal use and must not be used by applications.

This flag forces the redirector to use synchronous I/O even though the handle was opened for asynchronous I/O.

</td>
</tr>
</table>
 


## -remarks



For information about how to use ECPs to associate extra information with a file when the file is created, see <a href="https://msdn.microsoft.com/e32aeec6-1a0a-4d21-8358-89d9fc0a15eb">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. 

The NETWORK_OPEN_ECP_CONTEXT structure is read-only. You should use it to retrieve information about the network ECP context on a file only. For more information about this issue, see <a href="https://msdn.microsoft.com/6acb4be4-a7aa-431d-b2d8-3ef6d41cb4ef">System-Defined ECPs</a>.

If a caller must verify that the file system acknowledged the <b>NETWORK_OPEN_ECP_CONTEXT</b> context structure, the caller should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546808">FsRtlIsEcpAcknowledged</a> routine on the ECP after the operation is complete.

Drivers that run on Windows 7 and later versions of Windows and that must interpret network ECP contexts on files that reside on Windows Vista must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550899">NETWORK_OPEN_ECP_CONTEXT_V0</a> structure instead. Drivers that run on Windows Vista and later versions of Windows use the <b>NETWORK_OPEN_ECP_CONTEXT</b> structure to interpret network ECP contexts on files. However, the <b>DUMMYSTRUCTNAME.in.Flags</b> and <b>DUMMYSTRUCTNAME.out.Flags</b> members are only supported starting with Windows 7. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550899">NETWORK_OPEN_ECP_CONTEXT_V0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550902">NETWORK_OPEN_INTEGRITY_QUALIFIER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550908">NETWORK_OPEN_LOCATION_QUALIFIER</a>
 

 

