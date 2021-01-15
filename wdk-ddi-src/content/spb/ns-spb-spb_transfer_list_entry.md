---
UID: NS:spb.SPB_TRANSFER_LIST_ENTRY
title: SPB_TRANSFER_LIST_ENTRY (spb.h)
description: The SPB_TRANSFER_LIST_ENTRY structure describes a single transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_list_entry.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["SPB_TRANSFER_LIST_ENTRY structure"]
ms.keywords: "*PSPB_TRANSFER_LIST_ENTRY, PSPB_TRANSFER_LIST_ENTRY, PSPB_TRANSFER_LIST_ENTRY structure pointer [Buses], SPB.spb_transfer_list_entry, SPB_TRANSFER_LIST_ENTRY, SPB_TRANSFER_LIST_ENTRY structure [Buses], spb/PSPB_TRANSFER_LIST_ENTRY, spb/SPB_TRANSFER_LIST_ENTRY"
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
req.typenames: SPB_TRANSFER_LIST_ENTRY, *PSPB_TRANSFER_LIST_ENTRY
f1_keywords:
 - SPB_TRANSFER_LIST_ENTRY
 - spb/SPB_TRANSFER_LIST_ENTRY
 - PSPB_TRANSFER_LIST_ENTRY
 - spb/PSPB_TRANSFER_LIST_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_LIST_ENTRY
 - PSPB_TRANSFER_LIST_ENTRY
---

# SPB_TRANSFER_LIST_ENTRY structure


## -description

The <b>SPB_TRANSFER_LIST_ENTRY</b> structure describes a single transfer in an <a href="/windows-hardware/drivers/spb/i-o-transfer-sequences">I/O transfer sequence</a>.

## -struct-fields

### -field Direction

The direction of the transfer.  This member is set to one of the following <a href="/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_direction">SPB_TRANSFER_DIRECTION</a> enumeration values:

<ul>
<li><b>SpbTransferDirectionFromDevice</b></li>
<li><b>SpbTransferDirectionToDevice</b></li>
</ul>

### -field DelayInUs

An optional delay, in microseconds, before this transfer begins. For more information, see the description of the <b>DelayInUs</b> member in <a href="/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor">SPB_TRANSFER_DESCRIPTOR</a>.

### -field Buffer

The buffer for this transfer. This member uses one of the following buffer formats: simple buffer, scatter-gather list, or (for kernel-mode clients) MDL. For more information about buffer formats, see <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer">SPB_TRANSFER_BUFFER</a>.

## -remarks

To request an I/O transfer sequence for a target device on the bus, a client (peripheral driver) of the SPB controller driver sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a> request that describes the sequence. The transfers in the sequence are described by an <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list">SPB_TRANSFER_LIST</a> structure that is followed by an array of one or more <b>SPB_TRANSFER_LIST_ENTRY</b> structures. Each element in this array describes an individual transfer in the sequence.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer">SPB_TRANSFER_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor">SPB_TRANSFER_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_direction">SPB_TRANSFER_DIRECTION</a>



<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list">SPB_TRANSFER_LIST</a>

