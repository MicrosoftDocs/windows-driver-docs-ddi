---
UID: NS:wdm._TARGET_DEVICE_CUSTOM_NOTIFICATION
title: _TARGET_DEVICE_CUSTOM_NOTIFICATION (wdm.h)
description: The TARGET_DEVICE_CUSTOM_NOTIFICATION structure describes a custom device event.
old-location: kernel\target_device_custom_notification.htm
tech.root: kernel
ms.assetid: fa6530a4-13b7-472b-a571-682323edc64e
ms.date: 04/30/2018
keywords: ["TARGET_DEVICE_CUSTOM_NOTIFICATION structure"]
ms.keywords: "*PTARGET_DEVICE_CUSTOM_NOTIFICATION, PTARGET_DEVICE_CUSTOM_NOTIFICATION, PTARGET_DEVICE_CUSTOM_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], TARGET_DEVICE_CUSTOM_NOTIFICATION, TARGET_DEVICE_CUSTOM_NOTIFICATION structure [Kernel-Mode Driver Architecture], _TARGET_DEVICE_CUSTOM_NOTIFICATION, kernel.target_device_custom_notification, kstruct_d_b83ddfbd-9448-4a91-8a64-ab060ba7614f.xml, wdm/PTARGET_DEVICE_CUSTOM_NOTIFICATION, wdm/TARGET_DEVICE_CUSTOM_NOTIFICATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.typenames: TARGET_DEVICE_CUSTOM_NOTIFICATION, *PTARGET_DEVICE_CUSTOM_NOTIFICATION
f1_keywords:
 - _TARGET_DEVICE_CUSTOM_NOTIFICATION
 - wdm/_TARGET_DEVICE_CUSTOM_NOTIFICATION
 - PTARGET_DEVICE_CUSTOM_NOTIFICATION
 - wdm/PTARGET_DEVICE_CUSTOM_NOTIFICATION
 - TARGET_DEVICE_CUSTOM_NOTIFICATION
 - wdm/TARGET_DEVICE_CUSTOM_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - TARGET_DEVICE_CUSTOM_NOTIFICATION
---

# _TARGET_DEVICE_CUSTOM_NOTIFICATION structure


## -description

The <b>TARGET_DEVICE_CUSTOM_NOTIFICATION</b> structure describes a custom device event.

## -struct-fields

### -field Version

Specifies the version of the data structure, currently 1.

### -field Size

Specifies the size of the structure, in bytes, including the first three standard members plus the event-specific data.

### -field Event

Specifies a GUID identifying the event. GUIDs for custom event notification are defined by the components that use this mechanism.

### -field FileObject

Pointer to a file object for the device.

### -field NameBufferOffset

Specifies the offset, in bytes, from beginning of <b>CustomDataBuffer</b> where text begins. A value of -1 indicates that there is no text.

### -field CustomDataBuffer

A variable-length buffer, optionally containing binary data at the start of the buffer, followed by an optional text buffer (word-aligned).

## -remarks

Kernel-mode components use this structure for custom event notification:  to signal a custom event (<b>IoReportTargetDeviceChange</b>[<b>Asynchronous</b>]) and when handling a custom event (in a notification callback routine).

This structure accommodates both a variable-length binary data buffer and a variable-length Unicode text buffer. The <i>NameBufferOffset</i> must indicate where the text buffer begins, so the data can be delivered in the appropriate format (ANSI or Unicode) to user-mode applications that registered for handle-based notification with <b>RegisterDeviceNotification</b>. See the Microsoft Windows SDK documentation for information about <b>RegisterDeviceNotification</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreporttargetdevicechange">IoReportTargetDeviceChange</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreporttargetdevicechangeasynchronous">IoReportTargetDeviceChangeAsynchronous</a>