---
UID: NS:wdfdevice._WDF_FILEOBJECT_CONFIG
title: _WDF_FILEOBJECT_CONFIG (wdfdevice.h)
description: The WDF_FILEOBJECT_CONFIG structure contains configuration information of a driver's framework file objects.
old-location: wdf\wdf_fileobject_config.htm
tech.root: wdf
ms.assetid: 6fefc35f-fbbd-4c5e-bb8f-25ad3b6cdb67
ms.date: 02/26/2018
ms.keywords: "*PWDF_FILEOBJECT_CONFIG, DFDeviceObjectGeneralRef_5f843338-f299-48d3-80ad-d5d35c122d0f.xml, PWDF_FILEOBJECT_CONFIG, PWDF_FILEOBJECT_CONFIG structure pointer, WDF_FILEOBJECT_CONFIG, WDF_FILEOBJECT_CONFIG structure, _WDF_FILEOBJECT_CONFIG, kmdf.wdf_fileobject_config, wdf.wdf_fileobject_config, wdfdevice/PWDF_FILEOBJECT_CONFIG, wdfdevice/WDF_FILEOBJECT_CONFIG"
ms.topic: struct
f1_keywords:
 - "wdfdevice/WDF_FILEOBJECT_CONFIG"
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
- WDF_FILEOBJECT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_FILEOBJECT_CONFIG, *PWDF_FILEOBJECT_CONFIG
---

# _WDF_FILEOBJECT_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_FILEOBJECT_CONFIG</b> structure contains configuration information of a driver's framework file objects. 


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceFileCreate

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function, or <b>NULL</b>.


### -field EvtFileClose

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback function, or <b>NULL</b>.


### -field EvtFileCleanup

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a> callback function, or <b>NULL</b>.


### -field AutoForwardCleanupClose

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value. For more information about this member, see the following Comments section.


### -field FileObjectClass

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ne-wdfdevice-_wdf_fileobject_class">WDF_FILEOBJECT_CLASS</a>-typed value that identifies whether the driver requires a framework file object to represent each file that an application or another driver creates or opens. Additionally, this value specifies where the framework can store the object's handle. 


## -remarks



The <b>WDF_FILEOBJECT_CONFIG</b> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

<b>WDF_FILEOBJECT_CONFIG</b> must be initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdf_fileobject_config_init">WDF_FILEOBJECT_CONFIG_INIT</a>.

<h3><a id="Framework_Behavior_for_AutoForwardCleanupClose"></a><a id="framework_behavior_for_autoforwardcleanupclose"></a><a id="FRAMEWORK_BEHAVIOR_FOR_AUTOFORWARDCLEANUPCLOSE"></a>Framework Behavior for <b>AutoForwardCleanupClose</b></h3>
If <b>AutoForwardCleanupClose</b> is set to <b>WdfTrue</b>, the framework does the following:

<ul>
<li>
The framework forwards file creation requests to the next-lower driver if the driver does not provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function and has not called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a> to set an I/O queue to receive file creation requests. The framework does not forward file creation requests if the driver provides a callback function or a queue to handle the requests, so the driver must <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">forward</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">complete</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">cancel</a> the requests.

</li>
<li>
The framework sends file cleanup and close requests to the next-lower driver after calling the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback functions.

</li>
</ul>
If <b>AutoForwardCleanupClose</b> is set to <b>WdfFalse</b>, the framework does not forward file creation, cleanup, or close requests. Instead, the framework completes the requests for the driver.

If <b>AutoForwardCleanupClose</b> is set to <b>WdfUseDefault</b>, the framework uses <b>WdfTrue</b> behavior for filter drivers and <b>WdfFalse</b> behavior for function drivers.

<h3><a id="Driver_Behavior_for_AutoForwardCleanupClose"></a><a id="driver_behavior_for_autoforwardcleanupclose"></a><a id="DRIVER_BEHAVIOR_FOR_AUTOFORWARDCLEANUPCLOSE"></a>Driver Behavior for <b>AutoForwardCleanupClose</b></h3>
Your driver's local I/O target must always receive an equal number of I/O requests with request types of <b>WdfRequestTypeCreate</b>, <b>WdfRequestTypeCleanup</b>, and <b>WdfRequestTypeClose</b>. Therefore, if the driver provides either an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function or an I/O queue that receives file creation requests, you must use the following rules:

<ul>
<li>
If your driver sets <b>AutoForwardCleanupClose</b> to <b>WdfTrue</b>, the driver must forward all file creation requests to the local I/O target. You must follow this rule because the framework will forward all cleanup and close requests to the local target, whether or not your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback functions.

</li>
<li>
If your driver sets <b>AutoForwardCleanupClose</b> to <b>WdfFalse</b>, the driver must <i>not</i> forward file creation requests to the local I/O target. You must follow this rule because the framework will <i>not</i> forward cleanup and close requests to the local target, whether or not your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback functions.

</li>
<li>
If your driver sets <b>AutoForwardCleanupClose</b> to <b>WdfDefault</b>, the driver must follow the rule for <b>WdfTrue</b> if it is a filter driver. The driver must follow the rule for <b>WdfFalse</b> if it is a function driver.

</li>
</ul>


