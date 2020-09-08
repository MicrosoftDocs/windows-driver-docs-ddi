---
UID: NS:bthioctl._BTH_COMMAND_HEADER
title: _BTH_COMMAND_HEADER (bthioctl.h)
description: The BTH_COMMAND_HEADER structure specifies header information for a vendor-specific HCI command.
old-location: bltooth\bth_command_header.htm
tech.root: bltooth
ms.assetid: 2ed2196f-a966-4766-9acd-f0beca20ed26
ms.date: 04/27/2018
keywords: ["BTH_COMMAND_HEADER structure"]
ms.keywords: "*PBTH_COMMAND_HEADER, BTH_COMMAND_HEADER, BTH_COMMAND_HEADER structure [Bluetooth Devices], PBTH_COMMAND_HEADER, PBTH_COMMAND_HEADER structure pointer [Bluetooth Devices], _BTH_COMMAND_HEADER, bltooth.bth_command_header, bth_ref_cfbf5d5d-0362-4b8d-9f64-c9f1ad20284b.xml, bthioctl/BTH_COMMAND_HEADER, bthioctl/PBTH_COMMAND_HEADER"
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
req.typenames: BTH_COMMAND_HEADER, *PBTH_COMMAND_HEADER
f1_keywords:
 - _BTH_COMMAND_HEADER
 - bthioctl/_BTH_COMMAND_HEADER
 - PBTH_COMMAND_HEADER
 - bthioctl/PBTH_COMMAND_HEADER
 - BTH_COMMAND_HEADER
 - bthioctl/BTH_COMMAND_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthioctl.h
api_name:
 - BTH_COMMAND_HEADER
---

# _BTH_COMMAND_HEADER structure


## -description

The BTH_COMMAND_HEADER structure specifies header information for a vendor-specific HCI
  command.

## -struct-fields

### -field OpCode

A USHORT value that specifies the operation code for the command.

### -field TotalParameterLength

The size, in bytes, of the command payload, which is the data that follows the BTH_COMMAND_HEADER
     structure.

## -remarks

The BTH_COMMAND_HEADER structure specifies header information in the 
    <b>HciHeader</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_specific_command">
    BTH_VENDOR_SPECIFIC_COMMAND</a> structure. It also provides the header information for the output of
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_hci_vendor_command">
    IOCTL_BTH_HCI_VENDOR_COMMAND</a> IOCTL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_vendor_specific_command">BTH_VENDOR_SPECIFIC_COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_hci_vendor_command">IOCTL_BTH_HCI_VENDOR_COMMAND</a>

