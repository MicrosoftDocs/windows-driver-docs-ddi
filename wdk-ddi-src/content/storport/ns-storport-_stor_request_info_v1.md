---
UID: NS:storport._STOR_REQUEST_INFO_V1
title: "_STOR_REQUEST_INFO_V1"
author: windows-driver-content
description: The _STOR_REQUEST_INFO_V1 structure contains details about the storage driver IO request associated with a SCSI request block (SRB). _STOR_REQUEST_INFO_V1 is returned by the StorPortGetRequestInfo routine.
old-location: storage\stor_request_info.htm
old-project: storage
ms.assetid: CCC429B7-88BB-4DC3-86BC-6A5FCD405A5D
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/PSTOR_REQUEST_INFO_V1, PSTOR_REQUEST_INFO_V1 structure pointer [Storage Devices], storage.stor_request_info, StorIoPriorityVeryLow, StorIoPriorityLow, PSTOR_REQUEST_INFO_V1, *PSTOR_REQUEST_INFO_V1, REQUEST_INFO_TEMPORARY_FLAG, STOR_REQUEST_INFO_V1, _STOR_REQUEST_INFO_V1, storport/_STOR_REQUEST_INFO_V1, STOR_REQUEST_INFO_V1 structure [Storage Devices], StorIoPriorityNormal, StorIoPriorityHigh, StorIoPriorityCritical, REQUEST_INFO_SEQUENTIAL_IO_FLAG, REQUEST_INFO_WRITE_THROUGH_FLAG, REQUEST_INFO_NO_CACHE_FLAG, REQUEST_INFO_PAGING_IO_FLAG, _STOR_REQUEST_INFO_V1 structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	Storport.h
apiname:
-	STOR_REQUEST_INFO_V1
product: Windows
targetos: Windows
req.typenames: "*PSTOR_REQUEST_INFO_V1, STOR_REQUEST_INFO_V1"
req.product: Windows 10 or later.
---

# _STOR_REQUEST_INFO_V1 structure


## -description



   The <b>_STOR_REQUEST_INFO_V1</b> structure contains details about the storage driver IO request associated  with a SCSI request block (SRB). <b>_STOR_REQUEST_INFO_V1</b> is returned by the  
  <a href="..\storport\nf-storport-storportgetrequestinfo.md">StorPortGetRequestInfo</a> routine.


## -syntax


````
typedef struct _STOR_REQUEST_INFO_V1 {
  USHORT                Version;
  USHORT                Size;
  STOR_IO_PRIORITY_HINT PriorityHint;
  ULONG                 Flags;
  ULONG                 Key;
  ULONG                 Length;
  BOOLEAN               IsWriteRequest;
  UCHAR                 Reserved[3];
} STOR_REQUEST_INFO_V1, *PSTOR_REQUEST_INFO_V1;
````


## -struct-fields




### -field Version

The version of this structure. Set this member to <b>STOR_REQUEST_INFO_VER_1</b>.


### -field Size

The size of this structure. Set this value to <b>sizeof</b>(STOR_REQUEST_INFO).


### -field PriorityHint

The priority hint set for the IO request.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="StorIoPriorityVeryLow"></a><a id="storiopriorityverylow"></a><a id="STORIOPRIORITYVERYLOW"></a><dl>
<dt><b>StorIoPriorityVeryLow</b></dt>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Very low priority.

</td>
</tr>
<tr>
<td width="40%"><a id="StorIoPriorityLow"></a><a id="storioprioritylow"></a><a id="STORIOPRIORITYLOW"></a><dl>
<dt><b>StorIoPriorityLow</b></dt>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Low priority.

</td>
</tr>
<tr>
<td width="40%"><a id="StorIoPriorityNormal"></a><a id="storioprioritynormal"></a><a id="STORIOPRIORITYNORMAL"></a><dl>
<dt><b>StorIoPriorityNormal</b></dt>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Normal priority.

</td>
</tr>
<tr>
<td width="40%"><a id="StorIoPriorityHigh"></a><a id="storiopriorityhigh"></a><a id="STORIOPRIORITYHIGH"></a><dl>
<dt><b>StorIoPriorityHigh</b></dt>
<dt>3</dt>
</dl>
</td>
<td width="60%">
High priority.

</td>
</tr>
<tr>
<td width="40%"><a id="StorIoPriorityCritical"></a><a id="storioprioritycritical"></a><a id="STORIOPRIORITYCRITICAL"></a><dl>
<dt><b>StorIoPriorityCritical</b></dt>
<dt>4</dt>
</dl>
</td>
<td width="60%">
Critical priority.

</td>
</tr>
</table> 


### -field Flags

Flags set for handling the request. May be a combination of these values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_NO_CACHE_FLAG"></a><a id="request_info_no_cache_flag"></a><dl>
<dt><b>REQUEST_INFO_NO_CACHE_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Non-cached writes are specified for this request.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_PAGING_IO_FLAG"></a><a id="request_info_paging_io_flag"></a><dl>
<dt><b>REQUEST_INFO_PAGING_IO_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Paging IO is specified for this request.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_SEQUENTIAL_IO_FLAG"></a><a id="request_info_sequential_io_flag"></a><dl>
<dt><b>REQUEST_INFO_SEQUENTIAL_IO_FLAG</b></dt>
</dl>
</td>
<td width="60%">
Reads or writes are sequential.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_TEMPORARY_FLAG"></a><a id="request_info_temporary_flag"></a><dl>
<dt><b>REQUEST_INFO_TEMPORARY_FLAG</b></dt>
</dl>
</td>
<td width="60%">
The file for this request is temporary.

</td>
</tr>
<tr>
<td width="40%"><a id="REQUEST_INFO_WRITE_THROUGH_FLAG"></a><a id="request_info_write_through_flag"></a><dl>
<dt><b>REQUEST_INFO_WRITE_THROUGH_FLAG</b></dt>
</dl>
</td>
<td width="60%">
No system buffering for the request.

</td>
</tr>
</table> 


### -field Key

The read or write key for the request.


### -field Length

The length of the data in this request.


### -field IsWriteRequest

True if this is a write request. Otherwise, false, if this is a read request.


### -field Reserved

Reserved.


## -remarks


The caller to <a href="..\storport\nf-storport-storportgetrequestinfo.md">StorPortGetRequestInfo</a> allocates the <b>STOR_REQUEST_INFO</b> structure. Prior to calling <b>StorPortGetRequestInfo</b>,  <b>Version</b> must be set to <b>STOR_REQUEST_INFO_VER_1</b> and <b>Size</b> must be set to <b>sizeof</b>(STOR_REQUEST_INFO). Otherwise, <b>StorPortGetRequestInfo</b> will return with a status of <b>STOR_STATUS_INVALID_PARAMETER</b>.



## -see-also

<a href="..\storport\nf-storport-storportgetrequestinfo.md">StorPortGetRequestInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20_STOR_REQUEST_INFO_V1 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

