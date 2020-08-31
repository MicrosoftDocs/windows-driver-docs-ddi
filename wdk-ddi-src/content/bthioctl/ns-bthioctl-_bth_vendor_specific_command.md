---
UID: NS:bthioctl._BTH_VENDOR_SPECIFIC_COMMAND
title: _BTH_VENDOR_SPECIFIC_COMMAND (bthioctl.h)
description: The BTH_VENDOR_SPECIFIC_COMMAND structure specifies a Bluetooth vendor-specific command.
old-location: bltooth\bth_vendor_specific_command.htm
tech.root: bltooth
ms.assetid: c37844d9-206a-4060-8b46-9afe691fe8f9
ms.date: 04/27/2018
keywords: ["BTH_VENDOR_SPECIFIC_COMMAND structure"]
ms.keywords: "*PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND structure [Bluetooth Devices], PBTH_VENDOR_SPECIFIC_COMMAND, PBTH_VENDOR_SPECIFIC_COMMAND structure pointer [Bluetooth Devices], _BTH_VENDOR_SPECIFIC_COMMAND, bltooth.bth_vendor_specific_command, bth_ref_568c918a-282f-48e0-994a-c49289976bb6.xml, bthioctl/BTH_VENDOR_SPECIFIC_COMMAND, bthioctl/PBTH_VENDOR_SPECIFIC_COMMAND"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Available in Windows Vista, and later versions of Windows.
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
targetos: Windows
req.typenames: BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND
f1_keywords:
 - _BTH_VENDOR_SPECIFIC_COMMAND
 - bthioctl/_BTH_VENDOR_SPECIFIC_COMMAND
 - PBTH_VENDOR_SPECIFIC_COMMAND
 - bthioctl/PBTH_VENDOR_SPECIFIC_COMMAND
 - BTH_VENDOR_SPECIFIC_COMMAND
 - bthioctl/BTH_VENDOR_SPECIFIC_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthioctl.h
api_name:
 - BTH_VENDOR_SPECIFIC_COMMAND
---

# _BTH_VENDOR_SPECIFIC_COMMAND structure


## -description

The BTH_VENDOR_SPECIFIC_COMMAND structure specifies a Bluetooth vendor-specific command.

## -struct-fields

### -field ManufacturerId

The manufacturer identifier of the radio. Radios that have this manufacturer identifier can
     receive the vendor-specific command.

### -field LmpVersion

A UCHAR that contains the link management protocol (LMP) version. If the LMP version of a radio is
     greater than this value, the command is sent to the radio. Otherwise, the radio does not receive the
     command. If 
     <b>LmpVersion</b> is zero, all radios will receive the vendor-specific command.

### -field MatchAnySinglePattern

A BOOLEAN value that specifies if all the patterns in the 
     <b>Data</b> member must match or only one pattern must match to associate an event with a vendor-specific
     command. If there are no patterns that are associated with a vendor-specific command, this member is
     ignored. If 
     <b>MatchAnySinglePattern</b> is <b>FALSE</b>, all the patterns must match to associate an event with the
     command. If 
     <b>MatchAnySinglePattern</b> is <b>TRUE</b>, matching any pattern associates an event with the command.

### -field HciHeader

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_command_header">BTH_COMMAND_HEADER</a> structure that
     contains information about the vendor-specific command that includes an operation code and buffer
     length. The buffer length should only include the size of the data to be sent to the radio. It should
     not include the size of the patterns.

### -field Data

A UCHAR array that contains the data and patterns for the command that is specified in the 
     <b>HciHeader</b> member. Patterns are specified with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_pattern">BTH_VENDOR_PATTERN</a> structures.

## -remarks

This BTH_VENDOR_SPECIFIC_COMMAND structure specifies the input buffer for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_hci_vendor_command">
    IOCTL_BTH_HCI_VENDOR_COMMAND</a> IOCTL. This IOCTL can be used to send vendor-specific commands to
    Bluetooth radios.

To specify the size of the HCI command data, use the
    <b>TotalParameterLength</b> member in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_command_header">BTH_COMMAND_HEADER</a> structure in the
    BTH_VENDOR_SPECIFIC_COMMAND structure's 
    <b>HciHeader</b> member.

Patterns are required if a vendor-specific command does not follow the standard HCI flow control and a
    vendor-specific event is generated in response to the vendor-specific command.

If patterns are required, the patterns follow the data to be sent to the radio in the 
    <b>Data</b> member buffer. Each pattern begins with a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_pattern">BTH_VENDOR_PATTERN</a> structure.

If such patterns are specified, the 
    <b>TotalParameterLength</b> member should not include the size of the patterns.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_command_header">BTH_COMMAND_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_pattern">BTH_VENDOR_PATTERN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_hci_vendor_command">IOCTL_BTH_HCI_VENDOR_COMMAND</a>

