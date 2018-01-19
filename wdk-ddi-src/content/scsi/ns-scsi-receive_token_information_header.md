---
UID: NS:scsi.RECEIVE_TOKEN_INFORMATION_HEADER
title: RECEIVE_TOKEN_INFORMATION_HEADER
author: windows-driver-content
description: The RECEIVE_TOKEN_INFORMATION_HEADER structure contains information returned as status from an offload data transfer operation.
old-location: storage\receive_token_information_header.htm
old-project: storage
ms.assetid: 3D8BF059-2063-499E-B287-41EE184A2264
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: RECEIVE_TOKEN_INFORMATION_HEADER, *PRECEIVE_TOKEN_INFORMATION_HEADER, RECEIVE_TOKEN_INFORMATION_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Scsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RECEIVE_TOKEN_INFORMATION_HEADER
req.alt-loc: scsi.h
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
req.typenames: *PRECEIVE_TOKEN_INFORMATION_HEADER, RECEIVE_TOKEN_INFORMATION_HEADER
req.product: Windows 10 or later.
---

# RECEIVE_TOKEN_INFORMATION_HEADER structure



## -description
The <b>RECEIVE_TOKEN_INFORMATION_HEADER</b> structure contains information returned as status from an offload data transfer operation.



## -syntax

````
typedef struct _RECEIVE_TOKEN_INFORMATION_HEADER {
  UCHAR AvailableData[4];
  UCHAR ResponseToServiceAction  :5;
  UCHAR Reserved1  :3;
  UCHAR OperationStatus  :7;
  UCHAR Reserved2   :1;
  UCHAR OperationCounter[2];
  UCHAR EstimatedStatusUpdateDelay[4];
  UCHAR CompletionStatus;
  UCHAR SenseDataFieldLength;
  UCHAR SenseDataLength;
  UCHAR TransferCountUnits;
  UCHAR TransferCount[8];
  UCHAR SegmentsProcessed[2];
  UCHAR Reserved3[6];
  UCHAR SenseData[ANYSIZE_ARRAY];
} RECEIVE_TOKEN_INFORMATION_HEADER, *PRECEIVE_TOKEN_INFORMATION_HEADER;
````


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

### -field SERVICE_ACTION_POPULATE_TOKEN

</td>
<td width="60%">
The response information is for a POPULATE TOKEN command.

</td>
</tr>
<tr>

### -field SERVICE_ACTION_WRITE_USING_TOKEN

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

### -field 0x01

</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">

### -field 0x02

</td>
<td width="60%">
The operation completed unsuccessfully.

</td>
</tr>
<tr>
<td width="40%">

### -field 0x04

</td>
<td width="60%">
The operation completed successfully but the copy initiator should verify that all data was transferred.

</td>
</tr>
<tr>
<td width="40%">

### -field 0x10

</td>
<td width="60%">
The operation is in progress. Foreground or background operation state is unknown.

</td>
</tr>
<tr>
<td width="40%">

### -field 0x11

</td>
<td width="60%">
The operation is in progress in the foreground.

</td>
</tr>
<tr>
<td width="40%">

### -field 0x12

</td>
<td width="60%">
The operation is in progress in the background.

</td>
</tr>
<tr>
<td width="40%">

### -field 0x60

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

### -field TRANSFER_COUNT_UNITS_BYTES

</td>
<td width="60%">
Transfer count is in bytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_KIBIBYTES

</td>
<td width="60%">
Transfer count is in kilobytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_MEBIBYTES

</td>
<td width="60%">
Transfer count is in megabytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_GIBIBYTES

</td>
<td width="60%">
Transfer count is in gigabytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_TEBIBYTES

</td>
<td width="60%">
Transfer count is in terabytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_PEBIBYTES

</td>
<td width="60%">
Transfer count is in petabytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_EXBIBYTES

</td>
<td width="60%">
Transfer count is in exabytes.

</td>
</tr>
<tr>

### -field TRANSFER_COUNT_UNITS_NUMBER_BLOCKS

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
If <b>RECEIVE_TOKEN_INFORMATION_HEADER</b> is for a POPULATE TOKEN command operation, and the command completed successfully, a <a href="..\scsi\ns-scsi-receive_token_information_response_header.md">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a> structure will also be present after <b>SenseData</b> at an offset of <b>SenseDataFieldLength</b> from the beginning of the <b>SenseData</b> array. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure will contain the token created as a representation of data (ROD) for the range parameters sent with the command.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.


## -see-also
<dl>
<dt>
<a href="..\scsi\ns-scsi-receive_token_information_response_header.md">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RECEIVE_TOKEN_INFORMATION_HEADER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

