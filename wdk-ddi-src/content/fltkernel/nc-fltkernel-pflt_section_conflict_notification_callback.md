---
UID: NC:fltkernel.PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK
title: PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK (fltkernel.h)
description: A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's SectionNotificationCallback routine.
old-location: ifsk\pflt_section_conflict_notification_callback.htm
tech.root: ifsk
ms.assetid: 22840772-7DFC-4339-9C06-4900E47048B4
ms.date: 04/25/2019
ms.keywords: PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK, SectionNotificationCallback, SectionNotificationCallback routine [Installable File System Drivers], fltkernel/SectionNotificationCallback, ifsk.pflt_section_conflict_notification_callback
f1_keywords:
 - "fltkernel/SectionNotificationCallback"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: The PFLT_CONTEXT_ALLOCATE_CALLBACK callback routine is available on Windows 8 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fltkernel.h
api_name:
- SectionNotificationCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK callback function

## -description

A minifilter driver can optionally register a routine of type PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK as the minifilter driver's *SectionNotificationCallback* routine. Certain file operations are incompatible with file sections. If a minifilter provides a *SectionNotificationCallback* routine, the callback is called when section conflicts occur.

## -parameters

### -param Instance [in]

An opaque instance pointer to the minifilter driver instance that is initiating the I/O operation.

### -param SectionContext [in]

A pointer to the section context that incurred a data scan section conflict.

### -param Data [in]

A pointer to a caller-allocated structure that contains the callback data.

## -returns

This callback routine returns STATUS_SUCCESS.

## -remarks

A minifilter registers for section conflict notifications by setting a *PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK* routine to the **SectionNotificationCallback** member of the [FLT_REGISTRATION](ns-fltkernel-_flt_registration.md) structure when registering a minifilter driver.

Certain situations can occur where holding a section open is incompatible with current file I/O. In particular, file I/O that triggers a cache purge can cause cache incoherency if the cache purge is prevented because of an open section.  A minifilter can provide this optional callback routine for notifications of these events. When a notification is received, the section can be closed to allow the conflicting I/O operation to continue.

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FLT_REGISTRATION](ns-fltkernel-_flt_registration.md)

[FltCreateSectionForDataScan](nf-fltkernel-fltcreatesectionfordatascan.md)

[FltRegisterFilter](nf-fltkernel-fltregisterfilter.md)
