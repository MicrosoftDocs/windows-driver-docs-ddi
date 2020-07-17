---
UID: NI:ks.IOCTL_KS_DISABLE_EVENT
title: IOCTL_KS_DISABLE_EVENT (ks.h)
description: An application can use IOCTL_KS_DISABLE_EVENT to rescind a previous request notification. The application specifies IOCTL_KS_DISABLE_EVENT in the IoControl parameter of a call to KsSynchronousDeviceControl.
old-location: stream\ioctl_ks_disable_event.htm
tech.root: stream
ms.assetid: 4e451d0c-6548-4735-833a-3972cf5e59c6
ms.date: 04/23/2018
keywords: ["IOCTL_KS_DISABLE_EVENT IOCTL"]
ms.keywords: IOCTL_KS_DISABLE_EVENT, IOCTL_KS_DISABLE_EVENT control, IOCTL_KS_DISABLE_EVENT control code [Streaming Media Devices], ks-ioctl_8b6cd750-3003-49b2-9b91-3edc1da6cf11.xml, ks/IOCTL_KS_DISABLE_EVENT, stream.ioctl_ks_disable_event
f1_keywords:
 - "ks/IOCTL_KS_DISABLE_EVENT"
 - "IOCTL_KS_DISABLE_EVENT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- IOCTL_KS_DISABLE_EVENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_DISABLE_EVENT IOCTL


## -description



An application can use IOCTL_KS_DISABLE_EVENT to rescind a previous request notification. The application specifies IOCTL_KS_DISABLE_EVENT in the <b>IoControl</b> parameter of a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-kssynchronousdevicecontrol">KsSynchronousDeviceControl</a>.




## -ioctlparameters




### -input-buffer

The application places a pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> in the <b>InBuffer</b> parameter. This is the location of the original KSEVENTDATA structure that the application instantiated at the enabling of the event. To disable all active events, a client specifies a <b>NULL</b> pointer and length of zero in the <b>InBuffer</b> and <b>InLength</b> parameters.


### -input-buffer-length

Length of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ni-ks-ioctl_ks_disable_event">IOCTL_KS_DISABLE_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdpc_item">KSDPC_ITEM</a>



<a href="https://docs.microsoft.com/previous-versions/ff561744(v=vs.85)">KSEVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item">KSEVENT_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_set">KSEVENT_SET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdisableevent">KsDisableEvent</a>
 

 

