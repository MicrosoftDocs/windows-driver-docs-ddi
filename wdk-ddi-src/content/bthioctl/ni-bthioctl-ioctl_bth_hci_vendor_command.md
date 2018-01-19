---
UID: NI:bthioctl.IOCTL_BTH_HCI_VENDOR_COMMAND
title: IOCTL_BTH_HCI_VENDOR_COMMAND
author: windows-driver-content
description: The IOCTL_BTH_HCI_VENDOR_COMMAND request allows Bluetooth applications to send vendor-specific commands to radios.
old-location: bltooth\ioctl_bth_hci_vendor_command.htm
old-project: bltooth
ms.assetid: 3b182835-ca62-482c-b82a-28c59f23fb55
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Available on Microsoft Windows Vista SP2 and later operating system   versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTH_HCI_VENDOR_COMMAND
req.alt-loc: Bthioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_HCI_VENDOR_COMMAND IOCTL



## -description

     The IOCTL_BTH_HCI_VENDOR_COMMAND request allows Bluetooth applications to send vendor-specific
     commands to radios.



## -syntax

````
typedef struct _BTH_VENDOR_EVENT_INFO {
  BTH_ADDR BthAddress;
  ULONG    EventSize;
  UCHAR    EventInfo[1];
} BTH_VENDOR_EVENT_INFO, *PBTH_VENDOR_EVENT_INFO;
````


## -ioctlparameters

### -input-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a 
      <a href="..\bthioctl\ns-bthioctl-_bth_vendor_specific_command.md">BTH_VENDOR_SPECIFIC_COMMAND</a> structure. The structure contains a manufacturer identifier, a link
      management protocol (LMP) version, an HCI command header, and the associated vendor command data that
      includes optional pattern data to match an event to the command.


### -input-buffer-length
The length of a 
      <a href="..\bthioctl\ns-bthioctl-_bth_vendor_specific_command.md">BTH_VENDOR_SPECIFIC_COMMAND</a> structure. 


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that contains the event data returned from the radio. The data is available in the <b>EventInfo</b> member of the <a href="..\bthioctl\ns-bthioctl-_bth_vendor_event_info.md">BTH_VENDOR_EVENT_INFO</a> structure.

The <b>EventSize</b> member provides the size of the vendor-specific event data returned from the radio.


### -output-buffer-length
The length of a <a href="..\bthioctl\ns-bthioctl-_bth_vendor_event_info.md">BTH_VENDOR_EVENT_INFO</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that
      holds the command response.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_BUFFER_TOO_SMALL

The input buffer that was passed was too small.

STATUS_INVALID_PARAMETER

The input buffer that was passed was invalid.

STATUS_PRIVILEGE_NOT_HELD

The caller does not have the required privileges.

STATUS_INSUFFICIENT_RESOURCES

There was insufficient memory available to process the request.

 


## -remarks
The IOCTL_BTH_HCI_VENDOR_COMMAND request provides a mechanism that allows vendors to create commands
    that are specific to their Bluetooth radios.

The manufacturer ID and link management protocol (LMP) version values that are in the 
    <a href="..\bthioctl\ns-bthioctl-_bth_vendor_specific_command.md">
    BTH_VENDOR_SPECIFIC_COMMAND</a> structure help to prevent the sending of vendor-specific commands to
    the wrong radio. The LMP version enables the vendors to send vendor-specific commands to radios that have
    a matching LMP version. If the LMP version is zero, all radios from that vendor will receive the
    vendor-specific command.

Patterns are required if a vendor-specific command does not follow the standard HCI flow control and a
    vendor-specific event is generated in response to the vendor-specific command.

If patterns are required, the command should be followed by 
    <a href="..\bthioctl\ns-bthioctl-_bth_vendor_pattern.md">BTH_VENDOR_PATTERN</a> structures for patterns
    that are present in the event. These patterns allow the Bluetooth driver stack to match vendor-specific
    events with the corresponding vendor-specific commands.

The BTH_VENDOR_PATTERN structure specifies such patterns that follow the vendor-specific command data
    that is specified in the 
    <b>Data</b> member of BTH_VENDOR_SPECIFIC_COMMAND structure. The maximum total size of all the patterns
    that follow the command should not be greater than 255.

The event that is generated because of this command is copied into the output buffer (including the
    event header).


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_command_header.md">BTH_COMMAND_HEADER</a>
</dt>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_vendor_pattern.md">BTH_VENDOR_PATTERN</a>
</dt>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_vendor_specific_command.md">BTH_VENDOR_SPECIFIC_COMMAND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_HCI_VENDOR_COMMAND control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

