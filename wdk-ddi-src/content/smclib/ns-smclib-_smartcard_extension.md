---
UID: NS:smclib._SMARTCARD_EXTENSION
title: "_SMARTCARD_EXTENSION" (smclib.h)
description: The SMARTCARD_EXTENSION structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures.
old-location: smartcrd\smartcard_extension.htm
tech.root: smartcrd
ms.assetid: 057d82a8-ce5d-416f-b753-297dcbac27b8
ms.date: 02/22/2018
ms.keywords: "*PSMARTCARD_EXTENSION, PSMARTCARD_EXTENSION, PSMARTCARD_EXTENSION structure pointer [Smart Card Reader Devices], SMARTCARD_EXTENSION, SMARTCARD_EXTENSION structure [Smart Card Reader Devices], _SMARTCARD_EXTENSION, scstruct_399a1231-e161-450e-b5e2-6fc6035c865f.xml, smartcrd.smartcard_extension, smclib/PSMARTCARD_EXTENSION, smclib/SMARTCARD_EXTENSION"
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	smclib.h
api_name:
-	SMARTCARD_EXTENSION
product:
- Windows
targetos: Windows
req.typenames: "*PSMARTCARD_EXTENSION, SMARTCARD_EXTENSION"
---

# _SMARTCARD_EXTENSION structure


## -description


The <b>SMARTCARD_EXTENSION</b> structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures.


## -struct-fields




### -field Version

Indicates the version of this structure. 


### -field VendorAttr

Contains information that identifies the reader driver, such as the vendor name, unit number, and serial number. 


### -field ReaderFunction

A pointer to an array of callback functions for readers. The callback functions that a vendor-supplied reader driver can implement. A reader driver makes these callback functions available for the smart card library routine, <a href="https://msdn.microsoft.com/f9ad4cb8-f3cf-4e74-9c8c-bfd73d247d37">SmartcardDeviceControl</a>, to call by storing pointers to them in the smart card device extension. <dl>
<dd><i>RDF_ATR_PARSE</i></dd>
<dd><i>RDF_CARD_EJECT</i></dd>
<dd><i>RDF_CARD_POWER</i></dd>
<dd><i>RDF_CARD_TRACKING</i></dd>
<dd><i>RDF_IOCTL_VENDOR</i></dd>
<dd><i>RDF_READER_SWALLOW</i></dd>
<dd><i>RDF_SET_PROTOCOL</i></dd>
<dd><i>RDF_TRANSMIT</i></dd>
</dl>For more information, see Remarks.


### -field CardCapabilities

Contains capabilities of the inserted smart card. 


### -field LastError

Not used.


### -field IoRequest


      A structure with the following members:
      
     


### -field IoRequest.Information

Contains the number of bytes returned. 


### -field IoRequest.RequestBuffer

A pointer to the data in the user's I/O request to be sent to the card. 


### -field IoRequest.RequestBufferLength

Indicates the number of bytes to send to the card. 


### -field IoRequest.ReplyBuffer

A pointer to the buffer that holds the data that is returned by the I/O request. 


### -field IoRequest.ReplyBufferLength

Indicates the number of bytes of the data that are returned by the I/O request. 


### -field MajorIoControlCode

Contains the major I/O control code. 


### -field MinorIoControlCode

Contains the minor I/O control code. 


### -field OsData

Contains information that is specific to the operating system and the driver type. 


### -field ReaderCapabilities

Contains the capabilities of the keyboard reader. 


### -field ReaderExtension

Contains data that is specifc to the smart card reader. 


### -field SmartcardReply

Contains data that comes from the reader. 


### -field SmartcardRequest

Contains the current command and the data that is sent to the smart card. 


### -field T0

Contains the data for use with the T=0 protocol. 


### -field T1

Contains the data that is used with the T=1 protocol. 


### -field PerfInfo

 


### -field Reserved

Reserved for system use.


## -remarks



This structure is passed to all callback functions.

 Individual callback functions are identified by a series of constant values that should be used as indexes into the <b>ReaderFunction</b> array.

<table>
<tr>
<th>Index</th>
<th>Description</th>
</tr>
<tr>
<td>RDF_ATR_PARSE</td>
<td>Optional. The RDF_ATR_PARSE parse function parses an answer-to-reset (ATR) for the smart card driver library when the driver library is unable to recognize or parse the smart card driver library.</td>
</tr>
<tr>
<td>RDF_CARD_EJECT</td>
<td>Optional. RDF_CARD_EJECT callback function

The RDF_CARD_EJECT callback function ejects an inserted smart card from the reader.</td>
</tr>
<tr>
<td>RDF_CARD_POWER</td>
<td>The RDF_CARD_POWER callback function resets or turns off an inserted smart card.It is mandatory for smart card reader drivers to implement this callback function. 

On input, the structure pointed to by <b>SmartcardExtension</b> should have the following member values: 



<dl>
<dt><a id="MajorIoControlCode"></a><a id="majoriocontrolcode"></a><a id="MAJORIOCONTROLCODE"></a><b>MajorIoControlCode</b></dt>
<dd>
Should have a value of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548907">IOCTL_SMARTCARD_POWER</a>.

</dd>
<dt><a id="IoRequest.ReplyBufferLength"></a><a id="iorequest.replybufferlength"></a><a id="IOREQUEST.REPLYBUFFERLENGTH"></a><b>IoRequest.ReplyBufferLength</b></dt>
<dd>
Should contain the length of the buffer.

</dd>
<dt><a id="MinorIoControlCode"></a><a id="minoriocontrolcode"></a><a id="MINORIOCONTROLCODE"></a><b>MinorIoControlCode</b></dt>
<dd>
Should have one of the following minor codes:



<dl>
<dt><a id="SCARD_COLD_RESET"></a><a id="scard_cold_reset"></a>SCARD_COLD_RESET</dt>
<dd>
Performs a cold reset of the smart card.

</dd>
<dt><a id="SCARD_WARM_RESET"></a><a id="scard_warm_reset"></a>SCARD_WARM_RESET</dt>
<dd>
Performs a warm reset of the smart card. 

</dd>
<dt><a id="SCARD_POWER_DOWN"></a><a id="scard_power_down"></a>SCARD_POWER_DOWN</dt>
<dd>
Turns off smart card power.

</dd>
</dl>
</dd>
</dl>
On output, the structure pointed to by <b>SmartcardExtension</b> should have the following values:



<dl>
<dt><a id="IoRequest.ReplyBuffer"></a><a id="iorequest.replybuffer"></a><a id="IOREQUEST.REPLYBUFFER"></a><b>IoRequest.ReplyBuffer</b></dt>
<dd>
Receives the ATR that is returned by the smart card. In addition, you must transfer the ATR to <i>SmartcardExtension-&gt;CardCapabilities.ATR.Buffer </i>so that the library can parse the ATR.

</dd>
<dt><a id="IoRequest.Information"></a><a id="iorequest.information"></a><a id="IOREQUEST.INFORMATION"></a><b>IoRequest.Information</b></dt>
<dd>
Receives the length of the ATR.

</dd>
<dt><a id="CardCapabilities.ATR.Length"></a><a id="cardcapabilities.atr.length"></a><a id="CARDCAPABILITIES.ATR.LENGTH"></a><b>CardCapabilities.ATR.Length</b></dt>
<dd>
Contains the length of the ATR.

</dd>
</dl>
</td>
</tr>
<tr>
<td>RDF_CARD_TRACKING</td>
<td>The RDF_CARD_TRACKING callback function installs an event handler to track every time a card is inserted in or removed from a card reader.It is mandatory for smart card reader drivers to implement this callback function. 

Upon receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/dn905521">IOCTL_SMARTCARD_IS_PRESENT</a> request, the driver library determines if the smart card is already present. If the smart card is present, the driver library completes the request with a status of STATUS_SUCCESS. If there is no smart card present, the driver library calls the reader driver's smart card tracking callback function, and the reader driver starts looking for the smart card. After initiating smart card tracking, the driver library marks the request as having a status of STATUS_PENDING. 

The driver library completes the request.

<b>WDM Device Drivers</b>

The corresponding WDM driver library adds a pointer to the request in <b>SmartcardExtension-&gt;OsData-&gt;NotificationIrp</b>. The reader driver must complete the request as soon as it detects that a smart card has been inserted or removed. The reader driver completes the request by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>, after which, the reader driver must set the <b>NotificationIrp</b> member of <b>SmartcardExtension -&gt; OsData</b> back to <b>NULL</b> to inform the driver library that the reader driver can accept further smart card tracking requests. 

Because this call can have an indefinite duration and the caller can terminate the request before it is complete, it is important to mark this IRP as cancelable.

<pre xml:space="preserve"><code>MyDriverCardSupervision(
SmartcardExtension, 
OtherParameters)
//
//    This function is called whenever the card status changes
//    For example, the card has been inserted or the card has been removed
//
{
    if (SmartcardExtension-&gt;OsData-&gt;NotificationOverlappedData != NULL){

        SmartcardCompleteCardTracking(SmartcardExtension);
    }
    //
    // Do additional tasks
    //
}</code></pre>
</td>
</tr>
<tr>
<td>RDF_IOCTL_VENDOR</td>
<td>The RDF_IOCTL_VENDOR callback function performs vendor-specific IOCTL operations.It is optional for smart card reader drivers to implement this callback function. 

On input, the caller must pass the following values to the function:



<dl>
<dt><a id="SmartcardExtension-_MajorIoControlCode"></a><a id="smartcardextension-_majoriocontrolcode"></a><a id="SMARTCARDEXTENSION-_MAJORIOCONTROLCODE"></a><b>SmartcardExtension-&gt;MajorIoControlCode</b></dt>
<dd>
Contains a vendor-specific IOCTL code. Refer to the macro SCARD_CTL_CODE in <i>Winsmcrd.h</i> for information about how to define a vendor-specific IOCTL code. Note that the code must be between 2048 and 4095.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.RequestBuffer"></a><a id="smartcardextension-_iorequest.requestbuffer"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REQUESTBUFFER"></a><b>SmartcardExtension-&gt;IoRequest.RequestBuffer</b></dt>
<dd>
A pointer to the user's input buffer.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.RequestBufferLength"></a><a id="smartcardextension-_iorequest.requestbufferlength"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REQUESTBUFFERLENGTH"></a><b>SmartcardExtension-&gt;IoRequest.RequestBufferLength</b></dt>
<dd>
The size, in bytes, of the user's input buffer.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.ReplyBuffer"></a><a id="smartcardextension-_iorequest.replybuffer"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REPLYBUFFER"></a><b>SmartcardExtension-&gt;IoRequest.ReplyBuffer</b></dt>
<dd>
A pointer to the user's output buffer.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.ReplyBufferLength"></a><a id="smartcardextension-_iorequest.replybufferlength"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REPLYBUFFERLENGTH"></a><b>SmartcardExtension-&gt;IoRequest.ReplyBufferLength</b></dt>
<dd>
The size, in bytes, of the user's output buffer.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.Information"></a><a id="smartcardextension-_iorequest.information"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.INFORMATION"></a><b>SmartcardExtension-&gt;IoRequest.Information</b></dt>
<dd>
The value supplied by the request. Must be set to the number of bytes returned.

</dd>
</dl>
As with all other IOCTLs, a user-mode application dispatches a vendor-defined IOCTL to a smart card reader device by calling the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function. When the IOCTL is vendor-defined, however, the application must first open the reader device for "overlapped" (that is, asynchronous) access. The application must also define an OVERLAPPED structure and pass it to the system in the last argument of <b>DeviceIoControl</b> (The OVERLAPPED structure is also described in the Windows SDK documentation.). When the operating system calls the driver's I/O control dispatch routine, it passes a DIOCPARAMETERS structure to the driver. The <b>lpoOverlapped</b> member of the DIOCPARAMETERS structure contains a pointer to the OVERLAPPED structure. 

</td>
</tr>
<tr>
<td>RDF_READER_SWALLOW</td>
<td>The RDF_READER_SWALLOW callback function performs a mechanical swallow, which is what happens when the smart card is fully inserted into the smart card reader.It is optional for smart card reader drivers to implement this callback function. 

</td>
</tr>
<tr>
<td>RDF_SET_PROTOCOL</td>
<td>The RDF_SET_PROTOCOL callback function selects a transmission protocol for the inserted smart card.Smart card reader drivers must implement this callback function. 

On input, the caller must pass the following values to the function:



<dl>
<dt><a id="SmartcardExtension-_MajorIoControlCode"></a><a id="smartcardextension-_majoriocontrolcode"></a><a id="SMARTCARDEXTENSION-_MAJORIOCONTROLCODE"></a><b>SmartcardExtension-&gt;MajorIoControlCode</b></dt>
<dd>
Contains <a href="https://msdn.microsoft.com/library/windows/hardware/ff548909">IOCTL_SMARTCARD_SET_PROTOCOL</a>.

</dd>
<dt><a id="SmartcardExtension-_MinorIoControlCode"></a><a id="smartcardextension-_minoriocontrolcode"></a><a id="SMARTCARDEXTENSION-_MINORIOCONTROLCODE"></a><b>SmartcardExtension-&gt;MinorIoControlCode</b></dt>
<dd>
Contains a bitwise OR of one or more protocols than the caller accepts. The driver must select a protocol that the inserted smart card supports. We recommend that the T = 1 protocol is given precedence over the T = 0 protocol. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SCARD_PROTOCOL_RAW

</td>
<td>
Selects the raw protocol.

</td>
</tr>
<tr>
<td>
SCARD_PROTOCOL_T0

</td>
<td>
Selects the ISO T = 0 protocol.

</td>
</tr>
<tr>
<td>
SCARD_PROTOCOL_T1

</td>
<td>
Selects the ISO T = 1 protocol.

</td>
</tr>
</table>
 

</dd>
<dt><a id="SmartcardExtension-_IoRequest.ReplyBufferLength"></a><a id="smartcardextension-_iorequest.replybufferlength"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REPLYBUFFERLENGTH"></a><b>SmartcardExtension-&gt;IoRequest.ReplyBufferLength</b></dt>
<dd>
Contains the length of the reply buffer.

</dd>
<dt><a id="SmartcardExtension-_CardCapabilities.PtsData"></a><a id="smartcardextension-_cardcapabilities.ptsdata"></a><a id="SMARTCARDEXTENSION-_CARDCAPABILITIES.PTSDATA"></a><b>SmartcardExtension-&gt;CardCapabilities.PtsData</b></dt>
<dd>
Contains the required parameters to perform the PTS request. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548916">PTS_DATA</a>.

</dd>
</dl>
The request returns the following values:



<dl>
<dt><a id="SmartcardExtension-_IoRequest.ReplyBuffer"></a><a id="smartcardextension-_iorequest.replybuffer"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REPLYBUFFER"></a><b>SmartcardExtension-&gt;IoRequest.ReplyBuffer</b></dt>
<dd>
Contains the selected protocol.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.Information"></a><a id="smartcardextension-_iorequest.information"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.INFORMATION"></a><b>SmartcardExtension-&gt;IoRequest.Information</b></dt>
<dd>
Set to <b>sizeof</b>(ULONG).

</dd>
</dl>
The caller can supply a mask of acceptable protocols. The driver's set protocol callback routine selects one of the protocols in the mask and returns the selected protocol in <b>SmartcardExtension-&gt;IoRequest.ReplyBuffer</b>. 

</td>
</tr>
<tr>
<td>RDF_TRANSMIT</td>
<td>The RDF_TRANSMIT callback function performs data transmissions.Smart card reader drivers must implement this callback function. 

On input, the caller must pass the following values to the function:



<dl>
<dt><a id="SmartcardExtension-_MajorIoControlCode"></a><a id="smartcardextension-_majoriocontrolcode"></a><a id="SMARTCARDEXTENSION-_MAJORIOCONTROLCODE"></a><b>SmartcardExtension-&gt;MajorIoControlCode</b></dt>
<dd>
Contains <a href="https://msdn.microsoft.com/library/windows/hardware/ff548911">IOCTL_SMARTCARD_TRANSMIT</a>.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.RequestBuffer"></a><a id="smartcardextension-_iorequest.requestbuffer"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REQUESTBUFFER"></a><b>SmartcardExtension-&gt;IoRequest.RequestBuffer</b></dt>
<dd>
A pointer to an SCARD_IO_REQUEST structure followed by data to transmit to the card.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.RequestBufferLength"></a><a id="smartcardextension-_iorequest.requestbufferlength"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REQUESTBUFFERLENGTH"></a><b>SmartcardExtension-&gt;IoRequest.RequestBufferLength</b></dt>
<dd>
The number of bytes to transmit to the card.

</dd>
<dt><a id="SmartcardExtension-_IoRequest.ReplyBufferLength"></a><a id="smartcardextension-_iorequest.replybufferlength"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REPLYBUFFERLENGTH"></a><b>SmartcardExtension-&gt;IoRequest.ReplyBufferLength</b></dt>
<dd>
The size, in bytes, of the reply buffer.

</dd>
</dl>
The request returns the following values:



<dl>
<dt><a id="SmartcardExtension-_IoRequest.ReplyBuffer"></a><a id="smartcardextension-_iorequest.replybuffer"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.REPLYBUFFER"></a><b>SmartcardExtension-&gt;IoRequest.ReplyBuffer</b></dt>
<dd>
A pointer to the buffer that receives the SCARD_IO_REQUEST structure, plus the result of the card. 

</dd>
<dt><a id="SmartcardExtension-_IoRequest.Information"></a><a id="smartcardextension-_iorequest.information"></a><a id="SMARTCARDEXTENSION-_IOREQUEST.INFORMATION"></a><b>SmartcardExtension-&gt;IoRequest.Information</b></dt>
<dd>
Receives the actual number of bytes returned by the smart card, plus the size of the SCARD_IO_REQUEST structure. For a definition of the SCARD_IO_REQUEST structure, see IOCTL_SMARTCARD_TRANSMIT. 

</dd>
</dl>
When this function is called, <b>SmartcardExtension-&gt;IoRequest.RequestBuffer</b> points to an SCARD_IO_REQUEST structure followed by the data to transmit.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef struct _SCARD_IO_REQUEST{
  DWORD  dwProtocol;   // Protocol identifier
  DWORD  cbPciLength;  // Protocol Control Information Length
} SCARD_IO_REQUEST, *PSCARD_IO_REQUEST, *LPSCARD_IO_REQUEST;
    
   </pre>
</td>
</tr>
</table></span></div>
The <b>dwProtocol</b> member must contain the protocol identifier that is returned by a call to IOCTL_SMARTCARD_SET_PROTOCOL. 

The <b>cbPciLength</b> member contains the size, in bytes, of the SCARD_IO_REQUEST structure. The size of this structure is usually 8 bytes. 

The SCARD_IO_REQUEST structure is followed by (protocol) data to transmit to the card. Depending on the protocol to use for the transmission, the library offers several support functions. For more information about these support functions, see SmartcardT0Request (WDM) and SmartcardT1Request (WDM). 

<i>RequestBuffer</i> and <i>ReplyBuffer</i> point to the same system buffer. If you use the library function <i>SmartcardxxRequest</i> and <i>SmartcardxxReply</i>, you will not overwrite the input buffer. If you do not use these functions, make a copy of the <i>RequestBuffer</i> before you start transmissions.

You must copy the SCARD_IO_REQUEST structure to the <i>ReplyBuffer</i> parameter, followed by the data received from the card. Again, if you use the <i>SmartcardxxRequest</i> and <i>SmartcardxxReply</i> functions, the library will copy the structure for you.

</td>
</tr>
</table>
 



