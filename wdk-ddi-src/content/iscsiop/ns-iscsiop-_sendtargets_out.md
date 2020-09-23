---
UID: NS:iscsiop._SendTargets_OUT
title: _SendTargets_OUT (iscsiop.h)
description: The SendTargets_OUT structure holds the output data for the SendTargets method.
old-location: storage\sendtargets_out.htm
tech.root: storage
ms.assetid: 82efeeb9-1167-4114-9d88-7ef66f613f80
ms.date: 03/29/2018
keywords: ["SendTargets_OUT structure"]
ms.keywords: "*PSendTargets_OUT, PSendTargets_OUT, PSendTargets_OUT structure pointer [Storage Devices], SendTargets_OUT, SendTargets_OUT structure [Storage Devices], _SendTargets_OUT, iscsiop/PSendTargets_OUT, iscsiop/SendTargets_OUT, storage.sendtargets_out, structs-iSCSI_c54a2d75-d780-4605-bdaf-5953f7ce5008.xml"
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
targetos: Windows
req.typenames: SendTargets_OUT, *PSendTargets_OUT
f1_keywords:
 - _SendTargets_OUT
 - iscsiop/_SendTargets_OUT
 - PSendTargets_OUT
 - iscsiop/PSendTargets_OUT
 - SendTargets_OUT
 - iscsiop/SendTargets_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SendTargets_OUT
---

# _SendTargets_OUT structure


## -description

The SendTargets_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/sendtargets">SendTargets</a> method.

## -struct-fields

### -field Status

The status of the <b>SendTargets</b> method. This member will contain 0 if the SEND TARGETS operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the SEND TARGETS operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

### -field ResponseSize

The size, in bytes, of the buffer at Response.

### -field Response

A buffer that holds the response data that the target returns. Response to SendTargets in UTF8 characters. NOTE: This field is a variable length array.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/sendtargets">SendTargets</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_sendtargets_in">SendTargets_IN</a>