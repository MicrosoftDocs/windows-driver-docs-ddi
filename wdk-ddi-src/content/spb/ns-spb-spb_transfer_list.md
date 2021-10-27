---
UID: NS:spb.SPB_TRANSFER_LIST
title: SPB_TRANSFER_LIST (spb.h)
description: The SPB_TRANSFER_LIST structure describes an I/O transfer sequence.
old-location: spb\spb_transfer_list.htm
tech.root: SPB
ms.date: 09/13/2021
keywords: ["SPB_TRANSFER_LIST structure"]
ms.keywords: "*PSPB_TRANSFER_LIST, PSPB_TRANSFER_LIST, PSPB_TRANSFER_LIST structure pointer [Buses], SPB.spb_transfer_list, SPB_TRANSFER_LIST, SPB_TRANSFER_LIST structure [Buses], spb/PSPB_TRANSFER_LIST, spb/SPB_TRANSFER_LIST"
req.header: spb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.typenames: SPB_TRANSFER_LIST, *PSPB_TRANSFER_LIST
f1_keywords:
 - SPB_TRANSFER_LIST
 - spb/SPB_TRANSFER_LIST
 - PSPB_TRANSFER_LIST
 - spb/PSPB_TRANSFER_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_LIST
 - PSPB_TRANSFER_LIST
---

# SPB_TRANSFER_LIST structure

## -description

The **SPB_TRANSFER_LIST** structure describes an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences).

## -struct-fields

### -field Size

The size, in bytes, of the **SPB_TRANSFER_LIST** structure. This size value does not include any **Transfers** array elements that might follow this structure. If new members are added to future versions of this structure, the **Size** value can be used to determine which version of the **SPB_TRANSFER_LIST** structure is being used.

### -field Reserved

Reserved for use by the operating system. Set to zero.

### -field TransferCount

The number of elements in the **Transfers** array. This array contains a minimum of one element.

### -field Transfers

This member is the first element in an array of [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md) structures. Each array element describes an individual transfer in the I/O transfer sequence. If the array contains more than one element, the additional array elements immediately follow the **SPB_TRANSFER_LIST** structure in memory. The transfers are performed in the order in which they appear in the array, starting with the first element.

## -remarks

The input buffer for an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) request begins with an **SPB_TRANSFER_LIST** structure. The first transfer in the requested I/O transfer sequence is specified in the **Transfers** member of this structure. If the sequence contains more than one transfer, the array elements that describe the additional transfers immediately follow the **SPB_TRANSFER_LIST** structure.

The input buffer for an [IOCTL_SPB_FULL_DUPLEX](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_full_duplex-control-code) request begins with an **SPB_TRANSFER_LIST** structure. The **SPB_TRANSFER_LIST** structure for this request always specifies two buffers. The first buffer, which is described by the **Transfers** member of this structure, contains the data to write to the device. The second buffer, which is described by an array element that immediately follows the **SPB_TRANSFER_LIST** structure, is used to hold the data read from the device.

If your SPB controller driver supports custom I/O control (IOCTL) requests that use input or output buffers, use the **SPB_TRANSFER_LIST** structure to describe these buffers. For more information, see [Using the SPB_TRANSFER_LIST Structure for Custom IOCTLs](/windows-hardware/drivers/spb/using-the-spb-transfer-list-structure).

## -see-also

* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [IOCTL_SPB_FULL_DUPLEX](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_full_duplex-control-code)
* [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md)