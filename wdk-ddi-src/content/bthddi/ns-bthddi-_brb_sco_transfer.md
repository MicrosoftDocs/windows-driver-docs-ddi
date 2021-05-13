---
UID: NS:bthddi._BRB_SCO_TRANSFER
title: _BRB_SCO_TRANSFER (bthddi.h)
description: The _BRB_SCO_TRANSFER structure describes a buffer to read isochronous data from, or write isochronous data to a SCO channel.
old-location: bltooth\_brb_sco_transfer.htm
tech.root: bltooth
ms.date: 05/12/2021
keywords: ["BRB_SCO_TRANSFER structure"]
ms.keywords: "_BRB_SCO_TRANSFER, _BRB_SCO_TRANSFER structure [Bluetooth Devices], bltooth._brb_sco_transfer, bth_structs_2e4ed482-af73-4ca6-997c-53005c4fafc2.xml, bthddi/_BRB_SCO_TRANSFER"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.typenames: 
f1_keywords:
 - _BRB_SCO_TRANSFER
 - bthddi/_BRB_SCO_TRANSFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - _BRB_SCO_TRANSFER
---

# _BRB_SCO_TRANSFER structure

## -description

The _BRB_SCO_TRANSFER structure describes a buffer to read isochronous data from, or write isochronous data to a SCO channel.

## -struct-fields

### -field Hdr

A [BRB\_HEADER](/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header) structure that contains information about the current BRB.

### -field BtAddress

The Bluetooth address of the remote device.

### -field ChannelHandle

The SCO channel handle that was returned by Bluetooth driver stack in response to an earlier [BRB\_SCO\_OPEN\_CHANNEL](/previous-versions/ff536626(v=vs.85)) or [BRB\_SCO\_OPEN\_CHANNEL\_RESPONSE](/previous-versions/ff536627(v%3dvs.85)) request.

### -field TransferFlags

Flags that specify the basic behavior of the BRB. Valid flag values are listed in the following table.

| Flag | Description |
| ---- | ----------- |
| SCO_TRANSFER_DIRECTION_IN | If this bit is set, the BRB reads isochronous data from a remote device through the SCO channel. |
| SCO_TRANSFER_DIRECTION_OUT | If this bit is set, the BRB writes isochronous data to a remote device through the SCO channel. |

### -field BufferSize

The size, in bytes, of the input buffer described by the **Buffer** member of this structure.

### -field Buffer

A pointer to the input buffer. This value should be **NULL** when the **Buffer** member is not used.

### -field BufferMDL

A pointer to the MDL input buffer. This value should be **NULL** when the **BufferMDL** member is not used.

### -field DataTag

SCO write

## -remarks

To read isochronous data from or write isochronous data to a SCO connection, profile drivers should [build and send](/previous-versions/ff536657(v=vs.85)) a [BRB\_SCO\_TRANSFER](/previous-versions/ff536629(v=vs.85)) request.

Each SCO connection is bidirectional, and can be read from and written to simultaneously.

Read BRBs will remain pending until data arrives or until the profile driver flushes them. It is recommended that higher-level drivers have at least two pending read BRBs open at any time to accept incoming data from the remote device.

The Bluetooth driver stack does not provide any buffering for incoming isochronous data. Therefore a small gap between the completion of one read IRP and the submission of the next can cause data loss.

If both **Buffer** and **BufferMDL** contain non-**NULL** values, then **BufferMDL** takes precedence.

## -see-also

[BRB\_HEADER](/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header)

[BRB\_SCO\_OPEN\_CHANNEL](/previous-versions/ff536626(v=vs.85))

[BRB\_SCO\_OPEN\_CHANNEL\_RESPONSE](/previous-versions/ff536627(v%3dvs.85))

[BRB\_SCO\_TRANSFER](/previous-versions/ff536629(v=vs.85))
