---
UID: NS:scsi._SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE
title: "_SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE"
author: windows-driver-content
description: The SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE structure contains a vendor specific microcode (i.e., firmware) image for use by the enclosure services process.
old-location: storage\ses_download_microcode_control_diagnostic_page.htm
old-project: storage
ms.assetid: 09c2746f-cfe4-41dc-82ce-0b7e0c348897
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: Download microcode with offsets, save, and activate, Download microcode with offsets, save, and defer activate, Activate deferred microcode, scsi/SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, storage.ses_download_microcode_control_diagnostic_page, Reserved, _SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, *PSES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, scsi/PSES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, PSES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE structure pointer [Storage Devices], SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE structure [Storage Devices], SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, PSES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	scsi.h
apiname:
-	SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE
product: Windows
targetos: Windows
req.typenames: "*PSES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE"
req.product: Windows 10 or later.
---

# _SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE structure


## -description


The <b>SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</b> structure contains a vendor specific microcode (i.e., firmware) image
for use by the enclosure services process. 


## -syntax


````
typedef struct _SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE {
  UCHAR  PageCode;
  UCHAR  SubEnclosureId;
  UCHAR  PageLength[2];
  UCHAR  ExpectedGenerationCode[4];
  UCHAR  Mode;
  UCHAR  Reserved[2];
  UCHAR  BufferID;
  UCHAR  BufferOffset[4];
  UCHAR  ImageLength[4];
  UCHAR  DataLength[4];
  UCHAR  Data[ANYSIZE_ARRAY];
} SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE, *PSES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE;
````


## -struct-fields




### -field PageCode

Specifies the diagnostic page being sent or requested based on the value. For a Microcode Control diagnostic page, the value should be 0x0E.


### -field SubEnclosureId

Specifies the sub enclosure to which the application client is
sending the microcode image. If the value does not match a valid SUBENCLOSURE_IDENTIFIER field value found in the <a href="..\storport\ns-storport-_ses_configuration_diagnostic_page.md">SES_CONFIGURATION_DIAGNOSTIC_PAGE</a>, then the enclosure services
process shall abort the download microcode operation with a status of 0x80.


### -field PageLength

Specifies the number of bytes that follow in the diagnostic page.


### -field ExpectedGenerationCode

Specifies the expected value of the generation code. If this parameter is not set to the current generation code, then the enclosure services
process shall abort the download microcode operation with a status of 0x80. 


### -field Mode

Specifies which mode to download the microcode with. 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="Download_microcode_with_offsets__save__and_activate"></a><a id="download_microcode_with_offsets__save__and_activate"></a><a id="DOWNLOAD_MICROCODE_WITH_OFFSETS__SAVE__AND_ACTIVATE"></a><dl>
<dt><b>Download
microcode
with
offsets,
save, and
activate</b></dt>
<dt>0x07</dt>
</dl>
</td>
<td width="60%">
After the last SEND DIAGNOSTIC command delivers a Download Microcode
Control diagnostic page to the subenclosure completes, the enclosure services
process shall verify the complete microcode image (e.g., perform a vendor
specific checksum) and save the new microcode image into nonvolatile storage.

 If there are no errors in the microcode image or in the save operation, then the
enclosure services process shall perform one of the following actions:<ul>
<li>Set the <i>Status</i> field in <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>  to 0x10, if
requested, and activate the new microcode image after either returning the Download Microcode Status diagnostic page, power on, or for standalone enclosure services processes, a hard reset.</li>
<li>Set the <i>Status</i> field in <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>  to 0x11, if
requested,  and for standalone enclosure services processes only,
activate the new microcode image after either power on or hard reset.</li>
<li>Set the <i>Status</i> field in <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>  to 0x12, if
requested,  and activate the new microcode image after power on.</li>
</ul>


</td>
</tr>
<tr>
<td width="40%"><a id="Download_microcode_with_offsets__save__and_defer_activate"></a><a id="download_microcode_with_offsets__save__and_defer_activate"></a><a id="DOWNLOAD_MICROCODE_WITH_OFFSETS__SAVE__AND_DEFER_ACTIVATE"></a><dl>
<dt><b>Download
microcode
with
offsets,
save, and
defer
activate</b></dt>
<dt>0x0E</dt>
</dl>
</td>
<td width="60%">
After the last SEND DIAGNOSTIC command delivering a <b>SES_DOWNLOAD_MICROCODE_CONTROL_DIAGNOSTIC_PAGE</b> to the subenclosure completes, the enclosure services
process shall verify the complete microcode image (e.g., perform a vendor
specific checksum), save the new microcode image into nonvolatile storage
(e.g., flash ROM), and defer activation of the new microcode.


If there are no errors in the microcode image or in the save operation, then the
enclosure services process shall set the <i>Status</i> field in <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>  to 0x13 in the <a href="https://msdn.microsoft.com/4572040b-c234-4281-b9d7-14d7f2bb7506">SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE</a>, if
requested, and activate the new microcode after either:

<ul>
<li>Processing this structure with the
<i>Mode</i> field set to 0x0F (i.e., Activate deferred
microcode)</li>
<li>A power on</li>
<li>A hard reset</li>
</ul>
</td>
</tr>
<tr>
<td width="40%"><a id="Activate_deferred_microcode"></a><a id="activate_deferred_microcode"></a><a id="ACTIVATE_DEFERRED_MICROCODE"></a><dl>
<dt><b>Activate
deferred
microcode</b></dt>
<dt>0x0F</dt>
</dl>
</td>
<td width="60%">
After the SEND DIAGNOSTIC command specifying this mode completes, the
enclosure services process shall activate the deferred microcode image, if any.


</td>
</tr>
<tr>
<td width="40%"><a id="Reserved"></a><a id="reserved"></a><a id="RESERVED"></a><dl>
<dt><b>Reserved</b></dt>
<dt>All other values</dt>
</dl>
</td>
<td width="60%">
Reserved for future use.

</td>
</tr>
</table> 


### -field Reserved

Reserved for future use.


### -field BufferID

Specifies a specific buffer within the enclosure services process to receive the microcode
image. The enclosure services process assigns vendor specific buffer ID codes to buffers (e.g., the main
firmware image may be stored in buffer 00h and a backup firmware image may be stored in buffer 01h). The
enclosure services process shall support a buffer ID value of 00h. If more than one buffer is supported, then
the enclosure services process shall assign additional buffer ID codes contiguously, beginning with 01h. If the
enclosure services process receives an unsupported buffer ID code, then it shall abort the download
microcode operation and set the <i>Status</i> field in <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>  to 0x80 in the <a href="https://msdn.microsoft.com/4572040b-c234-4281-b9d7-14d7f2bb7506">SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE</a> structure.


### -field BufferOffset

Specifies the offset in bytes within the buffer to which the microcode data is written in multiples of four. The enclosure services process may require that this  field be contiguously increasing in consecutive SEND DIAGNOSTIC commands. 


### -field ImageLength

specifies the total number of bytes in the microcode image the application
intends to send to the specified <i>BufferID</i>.


### -field DataLength

Specifies the length of <i>Data</i>, in bytes.


### -field Data

Contains part of the vendor specific microcode image.

