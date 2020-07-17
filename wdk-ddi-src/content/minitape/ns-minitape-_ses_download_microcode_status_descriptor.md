---
UID: NS:minitape._SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR
title: _SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR (minitape.h)
description: The SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure specifies the status and additional status of a download microcode.
old-location: storage\ses_download_microcode_status_descriptor.htm
tech.root: storage
ms.assetid: af686e7a-9426-4151-8ac4-d95ae1689b4c
ms.date: 03/29/2018
keywords: ["_SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure"]
ms.keywords: "*PSES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, PSES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, PSES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure pointer [Storage Devices], SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure [Storage Devices], _SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, scsi/PSES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, scsi/SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, storage.ses_download_microcode_status_descriptor"
f1_keywords:
 - "minitape/SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR"
 - "SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR"
req.header: minitape.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
- scsi.h
api_name:
- SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR, *PSES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR
---

# _SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR structure


## -description


The <b>SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</b> structure specifies the status and additional status of a download microcode.


## -struct-fields




### -field Reserved1

Reserved for future use.


### -field SubEnclosureId

Specifies the subenclosure to which the download microcode
status descriptor applies to.


### -field Status

 Specifies the status of download microcode
operations for the subenclosure. After reporting a code indicating completion, the
enclosure services process shall set this field to 0x00 and shall
set the <i>AdditionalStatus</i> field to 0x00. Status may can contain one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
No download microcode operation is in progress.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
Download microcode operation is in progress. The enclosure services process has
received one or more Download Microcode Control diagnostic pages and is awaiting
additional microcode data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Download microcode operation data transfer is complete, currently updating nonvolatile
storage.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x03</dt>
</dl>
</td>
<td width="60%">
The enclosure services process is currently updating nonvolatile storage with deferred
microcode.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x04 to 0x0F</dt>
</dl>
</td>
<td width="60%">
Reserved for codes indicating interim status

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x10</dt>
</dl>
</td>
<td width="60%">
Download microcode operation complete with no error. The enclosure services process
begins using the new microcode after returning this status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x11</dt>
</dl>
</td>
<td width="60%">
Download microcode operation complete with no error. The enclosure services process
(e.g., a standalone enclosure services process) begins using the new microcode after the
next hard reset or power on.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x12</dt>
</dl>
</td>
<td width="60%">
Download microcode operation complete with no error. The enclosure services process
(e.g., an attached enclosure services process) begins using the new microcode after the
next power on.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x13</dt>
</dl>
</td>
<td width="60%">
Download microcode operation complete with no error. The enclosure services process
(e.g., an attached enclosure services process) begins using the new microcode after either processing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_control_diagnostic_page">SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</a> specifying the activate deferred microcode mode, hard reset, or power on.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x14 to 0x6F</dt>
</dl>
</td>
<td width="60%">
Reserved for codes indicating no error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x70 to 0x7F</dt>
</dl>
</td>
<td width="60%">
Vendor specific

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x80</dt>
</dl>
</td>
<td width="60%">
Error in one or more of the Download Microcode Control diagnostic page fields. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x81</dt>
</dl>
</td>
<td width="60%">
Specifies a Microcode image error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x82</dt>
</dl>
</td>
<td width="60%">
Download microcode timeout. The enclosure services process
may discard microcode data after a vendor specific amount of time, if it does not receive
the entire microcode image.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x83</dt>
</dl>
</td>
<td width="60%">
Internal error in the download microcode operation. New microcode image is needed
before a hard reset or power on

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x84</dt>
</dl>
</td>
<td width="60%">
Internal error in the download microcode operation. Hard reset and power on safe

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
Processed a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_control_diagnostic_page">SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</a> with the <i>Mode</i> field set to 0x0F (i.e., activate deferred microcode), if there is no deferred microcode.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0x86 to 0x0EF</dt>
</dl>
</td>
<td width="60%">
Reserved for codes indicating errors.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0xF0 to 0xFF</dt>
</dl>
</td>
<td width="60%">
Vendor Specific

</td>
</tr>
</table>
 


### -field AdditionalStatus

Provides an additional status value for certain
values of <i>Status</i> .


### -field MaximumImageSize

Indicates the maximum size in bytes of the
microcode image that the enclosure services process accepts. The image may be delivered using one or
more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_control_diagnostic_page">SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</a>.


### -field Reserved2

Reserved for future use.


### -field ExpectedBufferId

Indicates the next value that the
enclosure services process expects in the <i>BufferId</i> field in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_control_diagnostic_page">SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</a>.


### -field ExpectedBufferOffset

Indicates the next value that the
enclosure services process expects in the <i>BufferOffset</i> field in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_control_diagnostic_page">SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</a>. If the enclosure services process accepts arbitrary <i>BufferOffset</i> values, then it shall set <i>ExpectedBufferOffset</i> to 0xFFFFFFFF.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_control_diagnostic_page">SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</a>
 

 

