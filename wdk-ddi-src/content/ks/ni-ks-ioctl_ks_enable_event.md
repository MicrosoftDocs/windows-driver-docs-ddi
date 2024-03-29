---
UID: NI:ks.IOCTL_KS_ENABLE_EVENT
title: IOCTL_KS_ENABLE_EVENT (ks.h)
description: An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object.
old-location: stream\ioctl_ks_enable_event.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IOCTL_KS_ENABLE_EVENT IOCTL"]
ms.keywords: IOCTL_KS_ENABLE_EVENT, IOCTL_KS_ENABLE_EVENT control, IOCTL_KS_ENABLE_EVENT control code [Streaming Media Devices], ks-ioctl_7cc1eab4-2a30-4998-8f7d-122150800c9a.xml, ks/IOCTL_KS_ENABLE_EVENT, stream.ioctl_ks_enable_event
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: 
f1_keywords:
 - IOCTL_KS_ENABLE_EVENT
 - ks/IOCTL_KS_ENABLE_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - IOCTL_KS_ENABLE_EVENT
---

# IOCTL_KS_ENABLE_EVENT IOCTL


## -description

An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object. The application specifies IOCTL_KS_ENABLE_EVENT in the <b>IoControl</b> parameter of a call to <a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-kssynchronousdevicecontrol">KsSynchronousDeviceControl</a>.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The application places a pointer to a structure of type <a href="/windows-hardware/drivers/stream/ksevent-structure">KSEVENT</a> in the <b>InBuffer</b> parameter and the size of this structure at <b>InLength</b>.

### -input-buffer-length

Length of <a href="/windows-hardware/drivers/stream/ksevent-structure">KSEVENT</a>.

### -output-buffer

The application places a pointer to a structure of type <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> in the <b>OutBuffer</b> parameter and the size of this structure at <b>OutLength</b>.

### -output-buffer-length

Length of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.

## -remarks

To determine events supported by a KS object, specify <b>NULL</b> and 0 respectively for <b>InBuffer</b> and <b>InLength</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ni-ks-ioctl_ks_disable_event">IOCTL_KS_DISABLE_EVENT</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdpc_item">KSDPC_ITEM</a>



<a href="/windows-hardware/drivers/stream/ksevent-structure">KSEVENT</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_set">KSEVENT_SET</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdisableevent">KsDisableEvent</a>
