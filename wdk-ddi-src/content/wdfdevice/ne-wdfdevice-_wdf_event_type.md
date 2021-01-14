---
UID: NE:wdfdevice._WDF_EVENT_TYPE
title: _WDF_EVENT_TYPE (wdfdevice.h)
description: The WDF_EVENT_TYPE enumeration specifies.
old-location: wdf\wdf_event_type.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_EVENT_TYPE enumeration"]
ms.keywords: WDF_EVENT_TYPE, WDF_EVENT_TYPE enumeration, WdfEventBroadcast, WdfEventMaximum, WdfEventReserved, _WDF_EVENT_TYPE, wdf.wdf_event_type, wdfdevice/WDF_EVENT_TYPE, wdfdevice/WdfEventBroadcast, wdfdevice/WdfEventMaximum, wdfdevice/WdfEventReserved, wudfddi_types/WDF_EVENT_TYPE, wudfddi_types/WdfEventBroadcast, wudfddi_types/WdfEventMaximum, wudfddi_types/WdfEventReserved
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
req.typenames: WDF_EVENT_TYPE
f1_keywords:
 - _WDF_EVENT_TYPE
 - wdfdevice/_WDF_EVENT_TYPE
 - WDF_EVENT_TYPE
 - wdfdevice/WDF_EVENT_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
 - wudfddi_types.h
api_name:
 - _WDF_EVENT_TYPE
 - WDF_EVENT_TYPE
---

# _WDF_EVENT_TYPE enumeration (wdfdevice.h)


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_EVENT_TYPE</b> enumeration specifies  types of events about which a driver can notify a registered application.

## -enum-fields

### -field WdfEventReserved

Reserved for system use.

### -field WdfEventBroadcast

In the current version of UMDF, the driver must specify <b>WdfEventBroadcast</b>. For more information, see <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicepostevent">WdfDevicePostEvent</a>.

### -field WdfEventMaximum

Reserved for system use.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-postevent">IWDFDevice::PostEvent</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicepostevent">WdfDevicePostEvent</a>

