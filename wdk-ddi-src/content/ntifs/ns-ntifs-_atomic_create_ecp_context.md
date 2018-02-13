---
UID: NS:ntifs._ATOMIC_CREATE_ECP_CONTEXT
title: "_ATOMIC_CREATE_ECP_CONTEXT"
author: windows-driver-content
description: This structure allows supplemental operations to be performed on a file atomically during create.
old-location: ifsk\atomic_create_ecp_context.htm
old-project: ifsk
ms.assetid: CFA879CC-6124-4E1C-B440-358455A5E6EF
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/ATOMIC_CREATE_ECP_CONTEXT, ATOMIC_CREATE_ECP_IN_FLAG_BEST_EFFORT, ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED, ifsk.atomic_create_ecp_context, ATOMIC_CREATE_ECP_OUT_FLAG_EOF_SET, _ATOMIC_CREATE_ECP_CONTEXT, ATOMIC_CREATE_ECP_IN_FLAG_OPERATION_MASK, ATOMIC_CREATE_ECP_OUT_FLAG_REPARSE_POINT_SET, ATOMIC_CREATE_ECP_CONTEXT structure [Installable File System Drivers], ATOMIC_CREATE_ECP_CONTEXT, ntifs/PATOMIC_CREATE_ECP_CONTEXT, PATOMIC_CREATE_ECP_CONTEXT, ATOMIC_CREATE_ECP_IN_FLAG_SPARSE_SPECIFIED, ATOMIC_CREATE_ECP_IN_FLAG_REPARSE_POINT_SPECIFIED, PATOMIC_CREATE_ECP_CONTEXT structure pointer [Installable File System Drivers], ATOMIC_CREATE_ECP_OUT_FLAG_SPARSE_SET, ATOMIC_CREATE_ECP_OUT_FLAG_VDL_SET, ATOMIC_CREATE_ECP_OUT_FLAG_OPERATION_MASK, ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED, *PATOMIC_CREATE_ECP_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	ntifs.h
apiname:
-	ATOMIC_CREATE_ECP_CONTEXT
product: Windows
targetos: Windows
req.typenames: ATOMIC_CREATE_ECP_CONTEXT, *PATOMIC_CREATE_ECP_CONTEXT
---

# _ATOMIC_CREATE_ECP_CONTEXT structure


## -description


This structure allows supplemental
operations to be performed on a file atomically during create. Use the 


## -syntax


````
typedef struct _ATOMIC_CREATE_ECP_CONTEXT {
  USHORT                                                           Size;
  USHORT                                                           InFlags;
  USHORT                                                           OutFlags;
  USHORT                                                           ReparseBufferLength;
  _Field_size_bytes_opt_(ReparseBufferLength) PREPARSE_DATA_BUFFER ReparseBuffer;
  LONGLONG                                                         FileSize;
  LONGLONG                                                         ValidDataLength;
#if (NTDDI_VERSION >= NTDDI_WIN10_RS2)
  PFILE_TIMESTAMPS                                                 FileTimestamps;
#endif 
#if (NTDDI_VERSION >= NTDDI_WIN10_RS3)
  ULONG                                                            FileAttributes;
  ULONG                                                            UsnSourceInfo;
  USN                                                              Usn;
#endif 
} ATOMIC_CREATE_ECP_CONTEXT, *PATOMIC_CREATE_ECP_CONTEXT;
````


## -struct-fields




### -field Size

The size of the context structure.


### -field InFlags

Flags that indicate the requested supplemental operation(s) to be performed with the create operation.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_IN_FLAG_SPARSE_SPECIFIED"></a><a id="atomic_create_ecp_in_flag_sparse_specified"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_IN_FLAG_SPARSE_SPECIFIED</b></dt>
<dt>0x0001</dt>
</dl>
</td>
<td width="60%">
Requests that the sparse flag be set on the file.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_IN_FLAG_REPARSE_POINT_SPECIFIED"></a><a id="atomic_create_ecp_in_flag_reparse_point_specified"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_IN_FLAG_REPARSE_POINT_SPECIFIED</b></dt>
<dt>0x0002</dt>
</dl>
</td>
<td width="60%">
Requests that a reparse point be set on the file.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED"></a><a id="atomic_create_ecp_in_flag_eof_specified"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED</b></dt>
<dt>0x0004</dt>
</dl>
</td>
<td width="60%">
Requests that a file size be set on the file.  This also implies
that on-disk allocation will occur to support the requested file size.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED"></a><a id="atomic_create_ecp_in_flag_vdl_specified"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED</b></dt>
<dt>0x0008</dt>
</dl>
</td>
<td width="60%">
Requests that a valid data length be set on the file.  This also
implies that the file size be set to at least the requested valid data
length.  

<div class="alert"><b>Note</b>  This is considered a privileged operation if it could potentially
expose uninitialized data.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_IN_FLAG_OPERATION_MASK"></a><a id="atomic_create_ecp_in_flag_operation_mask"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_IN_FLAG_OPERATION_MASK</b></dt>
<dt>0x00ff</dt>
</dl>
</td>
<td width="60%">
Use this flag as a mask to specify the other <b>InFlags</b> flag values.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_IN_FLAG_BEST_EFFORT"></a><a id="atomic_create_ecp_in_flag_best_effort"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_IN_FLAG_BEST_EFFORT</b></dt>
<dt>0x0100</dt>
</dl>
</td>
<td width="60%">
Indicates that the  file system should perform the create operation even if some of the requested supplemental operations could not be
performed or are not supported by the file system. The caller may check
the <b>OutFlags</b> to see which operations were performed.  If this flag is not specified, the file system should fail the create operation if it cannot successfully
perform all of the requested supplemental operations.

</td>
</tr>
</table>
 


### -field OutFlags

Flags that indicate the actual supplemental operation(s) performed with a successful create operation.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_OUT_FLAG_SPARSE_SET"></a><a id="atomic_create_ecp_out_flag_sparse_set"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_OUT_FLAG_SPARSE_SET</b></dt>
<dt>0x0001</dt>
</dl>
</td>
<td width="60%">
Indicates that the sparse flag was set on the file.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_OUT_FLAG_REPARSE_POINT_SET"></a><a id="atomic_create_ecp_out_flag_reparse_point_set"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_OUT_FLAG_REPARSE_POINT_SET</b></dt>
<dt>0x0002</dt>
</dl>
</td>
<td width="60%">
Indicates that a reparse point was set on the file.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_OUT_FLAG_EOF_SET"></a><a id="atomic_create_ecp_out_flag_eof_set"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_OUT_FLAG_EOF_SET</b></dt>
<dt>0x0004</dt>
</dl>
</td>
<td width="60%">
Indicates that a file size was set on the file, and that on-disk allocation occurred to support the requested file size.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_OUT_FLAG_VDL_SET"></a><a id="atomic_create_ecp_out_flag_vdl_set"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_OUT_FLAG_VDL_SET</b></dt>
<dt>0x0008</dt>
</dl>
</td>
<td width="60%">
Indicates that a valid data length was set on the file, and that the file size was set to at least the requested valid data
length.

</td>
</tr>
<tr>
<td width="40%"><a id="ATOMIC_CREATE_ECP_OUT_FLAG_OPERATION_MASK"></a><a id="atomic_create_ecp_out_flag_operation_mask"></a><dl>
<dt><b>ATOMIC_CREATE_ECP_OUT_FLAG_OPERATION_MASK</b></dt>
<dt>0x00ff</dt>
</dl>
</td>
<td width="60%">
Use this flag value as a mask to determine the supplemental operations that were performed with the create operation.

</td>
</tr>
</table>
 


### -field ReparseBufferLength

The length of the <b>ReparseBuffer</b> member. This value can't exceed the <b>MAXIMUM_REPARSE_DATA_BUFFER_SIZE</b> (16K).


### -field ReparseBuffer

The optional value that indicates the type of buffer used in the create operation. Possible values are <b>REPARSE_DATA_BUFFER</b> or <b>REPARSE_GUID_DATA_BUFFER</b>.


### -field FileSize

The optional value that is used with <b>ATOMIC_CREATE_ECP_IN_FLAG_EOF_SPECIFIED</b> to indicate the requested file size to be set on the file.


### -field ValidDataLength

The optional value that is used with <b>ATOMIC_CREATE_ECP_IN_FLAG_VDL_SPECIFIED</b> to indicate the requested valid data length to be set on the file.


### -field FileTimestamps

Pointer to an optional <a href="..\ntifs\ns-ntifs-_file_timestamps.md">FILE_TIMESTAMPS</a> structure which contains  the last recorded instance of specific actions on a file.


### -field FileAttributes

Specifies the attributes of a file.


### -field UsnSourceInfo

Specifies optional Update Sequence Number (USN) source info flags.


### -field Usn

Specifies the Update Sequence Number (USN). This value is filled at the end of <b>GUID_ECP_ATOMIC_CREATE</b> .


## -remarks



The GUID used for this structure is the <b>GUID_ECP_ATOMIC_CREATE</b> (<code>4720bd83-52ac-4104-a130-d1ec6a8cc8e5</code>).



