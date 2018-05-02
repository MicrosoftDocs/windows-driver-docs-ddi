---
UID: NS:minitape.RECEIVE_TOKEN_INFORMATION_HEADER
title: RECEIVE_TOKEN_INFORMATION_HEADER
author: windows-driver-content
description: The RECEIVE_TOKEN_INFORMATION_HEADER structure contains information returned as status from an offload data transfer operation.
old-location: storage\receive_token_information_header.htm
old-project: storage
ms.assetid: 3D8BF059-2063-499E-B287-41EE184A2264
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PRECEIVE_TOKEN_INFORMATION_HEADER, PRECEIVE_TOKEN_INFORMATION_HEADER, PRECEIVE_TOKEN_INFORMATION_HEADER structure pointer [Storage Devices], RECEIVE_TOKEN_INFORMATION_HEADER, RECEIVE_TOKEN_INFORMATION_HEADER structure [Storage Devices], SERVICE_ACTION_POPULATE_TOKEN, SERVICE_ACTION_WRITE_USING_TOKEN, TRANSFER_COUNT_UNITS_BYTES, TRANSFER_COUNT_UNITS_EXBIBYTES, TRANSFER_COUNT_UNITS_GIBIBYTES, TRANSFER_COUNT_UNITS_KIBIBYTES, TRANSFER_COUNT_UNITS_MEBIBYTES, TRANSFER_COUNT_UNITS_NUMBER_BLOCKS, TRANSFER_COUNT_UNITS_PEBIBYTES, TRANSFER_COUNT_UNITS_TEBIBYTES, scsi/PRECEIVE_TOKEN_INFORMATION_HEADER, scsi/RECEIVE_TOKEN_INFORMATION_HEADER, storage.receive_token_information_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	scsi.h
api_name:
-	RECEIVE_TOKEN_INFORMATION_HEADER
product:
- Windows
targetos: Windows
req.typenames: RECEIVE_TOKEN_INFORMATION_HEADER, *PRECEIVE_TOKEN_INFORMATION_HEADER
---

# RECEIVE_TOKEN_INFORMATION_HEADER structure


## -description


The <b>RECEIVE_TOKEN_INFORMATION_HEADER</b> structure contains information returned as status from an offload data transfer operation.


## -struct-fields




### -field AvailableData

The amount of data available in the <b>SenseData</b> array and any additional result information.


### -field ResponseToServiceAction

A response code indicating which command action the response is for. The service action codes are the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SERVICE_ACTION_POPULATE_TOKEN"></a><a id="service_action_populate_token"></a><dl>
<dt><b>SERVICE_ACTION_POPULATE_TOKEN</b></dt>
</dl>
</td>
<td width="60%">
The response information is for a POPULATE TOKEN command.

</td>
</tr>
<tr>
<td width="40%"><a id="SERVICE_ACTION_WRITE_USING_TOKEN"></a><a id="service_action_write_using_token"></a><dl>
<dt><b>SERVICE_ACTION_WRITE_USING_TOKEN</b></dt>
</dl>
</td>
<td width="60%">
The response information is for a WRITE USING TOKEN command.

</td>
</tr>
</table>
 


### -field Reserved1

Reserved.


### -field OperationStatus

The current status of the copy operation. The status can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
The operation completed unsuccessfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
The operation completed successfully but the copy initiator should verify that all data was transferred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x10</dt>
</dl>
</td>
<td width="60%">
The operation is in progress. Foreground or background operation state is unknown.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x11</dt>
</dl>
</td>
<td width="60%">
The operation is in progress in the foreground.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x12</dt>
</dl>
</td>
<td width="60%">
The operation is in progress in the background.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x60</dt>
</dl>
</td>
<td width="60%">
The operation was terminated. Possibly by an existing resource reservation.

</td>
</tr>
</table>
 


### -field Reserved2

Reserved.


### -field OperationCounter

The number of commands processed for the current copy operation.


### -field EstimatedStatusUpdateDelay

The recommended time, in milliseconds, to wait before sending the next RECEIVE COPY STATUS command for updated information about the current copy operation.


### -field CompletionStatus

SCSI status code for the copy command operation.


### -field SenseDataFieldLength

The length, in bytes, of the entire data area available for sense data. This value is always &gt;=  <b>SenseDataLength</b>.


### -field SenseDataLength

The length, in bytes, of the data in <b>SenseData</b>.


### -field TransferCountUnits

The byte units applied to <i>TransferCount</i>. Each unit expansion is a exponent in base 2. The multiplier value of <b>TRANSFER_COUNT_UNITS_KIBIBYTES</b>, for example, is 1024 and not 1000. The defined units are the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_BYTES"></a><a id="transfer_count_units_bytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_BYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in bytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_KIBIBYTES"></a><a id="transfer_count_units_kibibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_KIBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in kilobytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_MEBIBYTES"></a><a id="transfer_count_units_mebibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_MEBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in megabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_GIBIBYTES"></a><a id="transfer_count_units_gibibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_GIBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in gigabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_TEBIBYTES"></a><a id="transfer_count_units_tebibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_TEBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in terabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_PEBIBYTES"></a><a id="transfer_count_units_pebibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_PEBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in petabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_EXBIBYTES"></a><a id="transfer_count_units_exbibytes"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_EXBIBYTES</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is in exabytes.

</td>
</tr>
<tr>
<td width="40%"><a id="TRANSFER_COUNT_UNITS_NUMBER_BLOCKS"></a><a id="transfer_count_units_number_blocks"></a><dl>
<dt><b>TRANSFER_COUNT_UNITS_NUMBER_BLOCKS</b></dt>
</dl>
</td>
<td width="60%">
Transfer count is not an exponent, but in units of logical block length.

</td>
</tr>
</table>
 


### -field TransferCount

The length of data transferred in the operation. The unit type in <b>TransferCountUnits</b> is applied to this value to give the total byte count.


### -field SegmentsProcessed

The number of segments processed for the data transfer operation. Segments are copy length units used internally by a storage device's copy provider. On Windowssystems, this value is reserved and applications must ignore this member.


### -field Reserved3

Reserved.


### -field SenseData

Sense data returned for the copy operation.


## -remarks



If <b>RECEIVE_TOKEN_INFORMATION_HEADER</b> is for a POPULATE TOKEN command operation, and the command completed successfully, a <a href="https://msdn.microsoft.com/library/windows/hardware/hh967732">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a> structure will also be present after <b>SenseData</b> at an offset of <b>SenseDataFieldLength</b> from the beginning of the <b>SenseData</b> array. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure will contain the token created as a representation of data (ROD) for the range parameters sent with the command.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh967732">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a>
 

 

