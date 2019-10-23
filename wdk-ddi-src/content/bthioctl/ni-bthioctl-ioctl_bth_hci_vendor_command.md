---
UID: NI:bthioctl.IOCTL_BTH_HCI_VENDOR_COMMAND
title: IOCTL_BTH_HCI_VENDOR_COMMAND (bthioctl.h)
description: The IOCTL_BTH_HCI_VENDOR_COMMAND request allows Bluetooth applications to send vendor-specific commands to radios.
old-location: bltooth\ioctl_bth_hci_vendor_command.htm
tech.root: bltooth
ms.assetid: 3b182835-ca62-482c-b82a-28c59f23fb55
ms.date: 04/27/2018
ms.keywords: IOCTL_BTH_HCI_VENDOR_COMMAND, IOCTL_BTH_HCI_VENDOR_COMMAND control, IOCTL_BTH_HCI_VENDOR_COMMAND control code [Bluetooth Devices], bltooth.ioctl_bth_hci_vendor_command, bth_ref_f907562d-11ca-4ec2-ace5-97042364bb01.xml, bthioctl/IOCTL_BTH_HCI_VENDOR_COMMAND
ms.topic: ioctl
f1_keywords:
 - "bthioctl/IOCTL_BTH_HCI_VENDOR_COMMAND"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Available on Microsoft Windows Vista SP2 and later operating system   versions.
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthioctl.h
api_name:
- IOCTL_BTH_HCI_VENDOR_COMMAND
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_HCI_VENDOR_COMMAND IOCTL


## -description



     The IOCTL_BTH_HCI_VENDOR_COMMAND request allows Bluetooth applications to send vendor-specific
     commands to radios.


## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_specific_command">BTH_VENDOR_SPECIFIC_COMMAND</a> structure. The structure contains a manufacturer identifier, a link
      management protocol (LMP) version, an HCI command header, and the associated vendor command data that
      includes optional pattern data to match an event to the command.


### -input-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_specific_command">BTH_VENDOR_SPECIFIC_COMMAND</a> structure. 


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that contains the event data returned from the radio. The data is available in the <b>EventInfo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_event_info">BTH_VENDOR_EVENT_INFO</a> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _BTH_VENDOR_EVENT_INFO {
  BTH_ADDR BthAddress;
  ULONG    EventSize;
  UCHAR    EventInfo[1];
} BTH_VENDOR_EVENT_INFO, *PBTH_VENDOR_EVENT_INFO;</pre>
</td>
</tr>
</table></span></div>
The <b>EventSize</b> member provides the size of the vendor-specific event data returned from the radio.


### -output-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_event_info">BTH_VENDOR_EVENT_INFO</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that
      holds the command response.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
STATUS_BUFFER_TOO_SMALL

</td>
<td>
The input buffer that was passed was too small.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
The input buffer that was passed was invalid.

</td>
</tr>
<tr>
<td>
STATUS_PRIVILEGE_NOT_HELD

</td>
<td>
The caller does not have the required privileges.

</td>
</tr>
<tr>
<td>
STATUS_INSUFFICIENT_RESOURCES

</td>
<td>
There was insufficient memory available to process the request.

</td>
</tr>
</table>
 


## -remarks



The IOCTL_BTH_HCI_VENDOR_COMMAND request provides a mechanism that allows vendors to create commands
    that are specific to their Bluetooth radios.

The manufacturer ID and link management protocol (LMP) version values that are in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_specific_command">
    BTH_VENDOR_SPECIFIC_COMMAND</a> structure help to prevent the sending of vendor-specific commands to
    the wrong radio. The LMP version enables the vendors to send vendor-specific commands to radios that have
    a matching LMP version. If the LMP version is zero, all radios from that vendor will receive the
    vendor-specific command.

Patterns are required if a vendor-specific command does not follow the standard HCI flow control and a
    vendor-specific event is generated in response to the vendor-specific command.

If patterns are required, the command should be followed by 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_pattern">BTH_VENDOR_PATTERN</a> structures for patterns
    that are present in the event. These patterns allow the Bluetooth driver stack to match vendor-specific
    events with the corresponding vendor-specific commands.

The BTH_VENDOR_PATTERN structure specifies such patterns that follow the vendor-specific command data
    that is specified in the 
    <b>Data</b> member of BTH_VENDOR_SPECIFIC_COMMAND structure. The maximum total size of all the patterns
    that follow the command should not be greater than 255.

<div class="alert"><b>Warning</b>  The process that submits IOCTL_BTH_HCI_VENDOR_COMMAND must have the
    SE_LOAD_DRIVER_NAME privilege. A process that is running in the system or an administrator context can
    elevate its privilege by using the SDK 
    <b>LookupPrivilegeValue</b> and 
    <b>AdjustTokenPrivileges</b> functions. The following code example demonstrates how to obtain this
    privilege. Note that the example does not demonstrate error handling.</div>
<div> </div>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HANDLE procToken;
LUID luid;
TOKEN_PRIVILEGES tp;

OpenProcessToken(GetCurrentProcess(), TOKEN_ADJUST_PRIVILEGES | TOKEN_QUERY, &procToken);

LookupPrivilegeValue(NULL, SE_LOAD_DRIVER_NAME, &luid);

Tp.PrivilegeCount = 1;
Tp.privileges[0].Luid = luid;
Tp.Privileges[0].Attributes = SE_PRIVILEGE_ENABLED;

AdjustTokenPrivileges(procToken, FALSE, &tp, sizeof(TOKEN_PRIVILEGES), (PTOKEN_PRIVILEGES) NULL, (PDWORD)NULL);</pre>
</td>
</tr>
</table></span></div>
The event that is generated because of this command is copied into the output buffer (including the
    event header).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_command_header">BTH_COMMAND_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_pattern">BTH_VENDOR_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_specific_command">BTH_VENDOR_SPECIFIC_COMMAND</a>
 

 

