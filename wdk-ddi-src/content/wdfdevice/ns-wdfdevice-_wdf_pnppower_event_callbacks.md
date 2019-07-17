---
UID: NS:wdfdevice._WDF_PNPPOWER_EVENT_CALLBACKS
title: _WDF_PNPPOWER_EVENT_CALLBACKS (wdfdevice.h)
description: The WDF_PNPPOWER_EVENT_CALLBACKS structure contains pointers to a driver's Plug and Play and power event callback functions.
old-location: wdf\wdf_pnppower_event_callbacks.htm
tech.root: wdf
ms.assetid: 2bfd677f-f2bd-49d7-b572-d7df4de0425c
ms.date: 02/26/2018
ms.keywords: "*PWDF_PNPPOWER_EVENT_CALLBACKS, DFDeviceObjectGeneralRef_a4b53707-d968-45a7-a5e8-284e9f34f866.xml, PWDF_PNPPOWER_EVENT_CALLBACKS, PWDF_PNPPOWER_EVENT_CALLBACKS structure pointer, WDF_PNPPOWER_EVENT_CALLBACKS, WDF_PNPPOWER_EVENT_CALLBACKS structure, _WDF_PNPPOWER_EVENT_CALLBACKS, kmdf.wdf_pnppower_event_callbacks, wdf.wdf_pnppower_event_callbacks, wdfdevice/PWDF_PNPPOWER_EVENT_CALLBACKS, wdfdevice/WDF_PNPPOWER_EVENT_CALLBACKS"
ms.topic: struct
f1_keywords:
 - "wdfdevice/WDF_PNPPOWER_EVENT_CALLBACKS"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
api_name:
- WDF_PNPPOWER_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: WDF_PNPPOWER_EVENT_CALLBACKS, *PWDF_PNPPOWER_EVENT_CALLBACKS
---

# _WDF_PNPPOWER_EVENT_CALLBACKS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_PNPPOWER_EVENT_CALLBACKS</b> structure contains pointers to a driver's Plug and Play and power event callback functions. 


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceD0Entry

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceD0EntryPostInterruptsEnabled

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled">EvtDeviceD0EntryPostInterruptsEnabled</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceD0Exit

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceD0ExitPreInterruptsDisabled

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled">EvtDeviceD0ExitPreInterruptsDisabled</a> event callback function, or <b>NULL</b>.


### -field EvtDevicePrepareHardware

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceReleaseHardware

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSelfManagedIoCleanup

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup">EvtDeviceSelfManagedIoCleanup</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSelfManagedIoFlush

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_flush">EvtDeviceSelfManagedIoFlush</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSelfManagedIoInit

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSelfManagedIoSuspend

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_suspend">EvtDeviceSelfManagedIoSuspend</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSelfManagedIoRestart

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_restart">EvtDeviceSelfManagedIoRestart</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceSurpriseRemoval

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_surprise_removal">EvtDeviceSurpriseRemoval</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceQueryRemove

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_query_remove">EvtDeviceQueryRemove</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceQueryStop

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_query_stop">EvtDeviceQueryStop</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceUsageNotification

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_usage_notification">EvtDeviceUsageNotification</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceRelationsQuery

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_relations_query">EvtDeviceRelationsQuery</a> event callback function, or <b>NULL</b>.


### -field EvtDeviceUsageNotificationEx

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_usage_notification_ex">EvtDeviceUsageNotificationEx</a> event callback function, or <b>NULL</b>. The <b>EvtDeviceUsageNotificationEx</b> member is available in version 1.11 and later versions of KMDF.
A driver can register either <b>EvtDeviceRelationsQuery</b> or <b>EvtDeviceUsageNotificationEx</b>, but not both.


## -remarks



The <b>WDF_PNPPOWER_EVENT_CALLBACKS</b> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a> method.

Your driver should initialize its WDF_PNPPOWER_EVENT_CALLBACKS structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdf_pnppower_event_callbacks_init">WDF_PNPPOWER_EVENT_CALLBACKS_INIT</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_power_policy_event_callbacks">WDF_POWER_POLICY_EVENT_CALLBACKS</a>
 

 

