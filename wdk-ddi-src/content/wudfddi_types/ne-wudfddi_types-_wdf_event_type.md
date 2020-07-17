---
UID: NE:wudfddi_types._WDF_EVENT_TYPE
title: _WDF_EVENT_TYPE (wudfddi_types.h)
description: The WDF_EVENT_TYPE enumeration specifies.
old-location: wdf\wdf_event_type.htm
tech.root: wdf
ms.assetid: DC6353BB-98C0-4647-9180-F099CD95348E
ms.date: 02/26/2018
keywords: ["_WDF_EVENT_TYPE enumeration"]
ms.keywords: WDF_EVENT_TYPE, WDF_EVENT_TYPE enumeration, WdfEventBroadcast, WdfEventMaximum, WdfEventReserved, _WDF_EVENT_TYPE, wdf.wdf_event_type, wdfdevice/WDF_EVENT_TYPE, wdfdevice/WdfEventBroadcast, wdfdevice/WdfEventMaximum, wdfdevice/WdfEventReserved, wudfddi_types/WDF_EVENT_TYPE, wudfddi_types/WdfEventBroadcast, wudfddi_types/WdfEventMaximum, wudfddi_types/WdfEventReserved
f1_keywords:
 - "wudfddi_types/WDF_EVENT_TYPE"
 - "WDF_EVENT_TYPE"
req.header: wudfddi_types.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
- wudfddi_types.h
api_name:
- WDF_EVENT_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_EVENT_TYPE
---

# _WDF_EVENT_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_EVENT_TYPE</b> enumeration specifies  types of events about which a driver can notify a registered application.


## -enum-fields




### -field WdfEventReserved

Reserved for system use.


### -field WdfEventBroadcast

In the current version of UMDF, the driver must specify <b>WdfEventBroadcast</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicepostevent">WdfDevicePostEvent</a>.


### -field WdfEventMaximum

Reserved for system use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-postevent">IWDFDevice::PostEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicepostevent">WdfDevicePostEvent</a>
 

 

