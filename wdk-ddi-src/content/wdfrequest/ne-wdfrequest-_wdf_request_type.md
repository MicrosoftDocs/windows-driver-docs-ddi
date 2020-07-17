---
UID: NE:wdfrequest._WDF_REQUEST_TYPE
title: _WDF_REQUEST_TYPE (wdfrequest.h)
description: The WDF_REQUEST_TYPE enumeration type identifies types of requests that a framework request object might contain.
old-location: wdf\wdf_request_type.htm
tech.root: wdf
ms.assetid: 91c036a0-7fce-4c7d-a217-eb1c487a15d0
ms.date: 02/26/2018
keywords: ["_WDF_REQUEST_TYPE enumeration"]
ms.keywords: DFRequestObjectRef_43f31fe0-45c1-45d2-adcc-d0d931327eeb.xml, WDF_REQUEST_TYPE, WDF_REQUEST_TYPE enumeration, WdfRequestTypeCleanup, WdfRequestTypeClose, WdfRequestTypeCreate, WdfRequestTypeCreateMailSlot, WdfRequestTypeCreateNamedPipe, WdfRequestTypeDeviceChange, WdfRequestTypeDeviceControl, WdfRequestTypeDeviceControlInternal, WdfRequestTypeDirectoryControl, WdfRequestTypeFileSystemControl, WdfRequestTypeFlushBuffers, WdfRequestTypeLockControl, WdfRequestTypeMax, WdfRequestTypeNoFormat, WdfRequestTypeOther, WdfRequestTypePnp, WdfRequestTypePower, WdfRequestTypeQueryEA, WdfRequestTypeQueryInformation, WdfRequestTypeQueryQuota, WdfRequestTypeQuerySecurity, WdfRequestTypeQueryVolumeInformation, WdfRequestTypeRead, WdfRequestTypeSetEA, WdfRequestTypeSetInformation, WdfRequestTypeSetQuota, WdfRequestTypeSetSecurity, WdfRequestTypeSetVolumeInformation, WdfRequestTypeShutdown, WdfRequestTypeSystemControl, WdfRequestTypeUsb, WdfRequestTypeWrite, _WDF_REQUEST_TYPE, kmdf.wdf_request_type, wdf.wdf_request_type, wdfrequest/WDF_REQUEST_TYPE, wdfrequest/WdfRequestTypeCleanup, wdfrequest/WdfRequestTypeClose, wdfrequest/WdfRequestTypeCreate, wdfrequest/WdfRequestTypeCreateMailSlot, wdfrequest/WdfRequestTypeCreateNamedPipe, wdfrequest/WdfRequestTypeDeviceChange, wdfrequest/WdfRequestTypeDeviceControl, wdfrequest/WdfRequestTypeDeviceControlInternal, wdfrequest/WdfRequestTypeDirectoryControl, wdfrequest/WdfRequestTypeFileSystemControl, wdfrequest/WdfRequestTypeFlushBuffers, wdfrequest/WdfRequestTypeLockControl, wdfrequest/WdfRequestTypeMax, wdfrequest/WdfRequestTypeNoFormat, wdfrequest/WdfRequestTypeOther, wdfrequest/WdfRequestTypePnp, wdfrequest/WdfRequestTypePower, wdfrequest/WdfRequestTypeQueryEA, wdfrequest/WdfRequestTypeQueryInformation, wdfrequest/WdfRequestTypeQueryQuota, wdfrequest/WdfRequestTypeQuerySecurity, wdfrequest/WdfRequestTypeQueryVolumeInformation, wdfrequest/WdfRequestTypeRead, wdfrequest/WdfRequestTypeSetEA, wdfrequest/WdfRequestTypeSetInformation, wdfrequest/WdfRequestTypeSetQuota, wdfrequest/WdfRequestTypeSetSecurity, wdfrequest/WdfRequestTypeSetVolumeInformation, wdfrequest/WdfRequestTypeShutdown, wdfrequest/WdfRequestTypeSystemControl, wdfrequest/WdfRequestTypeUsb, wdfrequest/WdfRequestTypeWrite
f1_keywords:
 - "wdfrequest/WDF_REQUEST_TYPE"
 - "WDF_REQUEST_TYPE"
req.header: wdfrequest.h
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
- wdfrequest.h
api_name:
- WDF_REQUEST_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
---

# _WDF_REQUEST_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_TYPE</b> enumeration type identifies types of requests that a framework request object might contain.


## -enum-fields




### -field WdfRequestTypeCreate

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a> callback function.


### -field WdfRequestTypeCreateNamedPipe

The request object represents an <b>IRP_MJ_CREATE_NAMED_PIPE</b> request. The framework does not handle this type of request.


### -field WdfRequestTypeClose

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a> callback function.


### -field WdfRequestTypeRead

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeWrite

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeQueryInformation

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetInformation

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-information">IRP_MJ_SET_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeQueryEA

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-ea">IRP_MJ_QUERY_EA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetEA

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-ea">IRP_MJ_SET_EA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeFlushBuffers

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers">IRP_MJ_FLUSH_BUFFERS</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeQueryVolumeInformation

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information">IRP_MJ_QUERY_VOLUME_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetVolumeInformation

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-volume-information">IRP_MJ_SET_VOLUME_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeDirectoryControl

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeFileSystemControl

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeDeviceControl

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeDeviceControlInternal

The request object represents an  <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeShutdown

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-shutdown">IRP_MJ_SHUTDOWN</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcontrol/nc-wdfcontrol-evt_wdf_device_shutdown_notification">EvtDeviceShutdownNotification</a> callback function, if it exists.


### -field WdfRequestTypeLockControl

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-lock-control">IRP_MJ_LOCK_CONTROL</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeCleanup

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a> callback function.


### -field WdfRequestTypeCreateMailSlot

The request object represents an <b>IRP_MJ_CREATE_MAILSLOT</b> request. The framework does not handle this type of request.


### -field WdfRequestTypeQuerySecurity

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-security">IRP_MJ_QUERY_SECURITY</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetSecurity

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-security">IRP_MJ_SET_SECURITY</a> request. The framework does not handle this type of request.


### -field WdfRequestTypePower

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/">general</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/">FDO</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/">PDO</a> callback functions for Plug and Play (PnP) and power management, if the callback functions exist.


### -field WdfRequestTypeSystemControl

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-system-control">IRP_MJ_SYSTEM_CONTROL</a> request. The framework handles this type of request for the driver, if the driver supports <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Windows Management Instrumentation (WMI)</a>.


### -field WdfRequestTypeDeviceChange

The request object represents an <b>IRP_MJ_DEVICE_CHANGE</b> request. The framework does not handle this type of request.


### -field WdfRequestTypeQueryQuota

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetQuota

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypePnp

The request object represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-pnp">IRP_MJ_PNP</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/">general</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/">FDO</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/">PDO</a> callback functions for PnP and power management, if the callback functions exist.


### -field WdfRequestTypeOther

A driver receives this request type in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> event callback function when requests formatted with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforinternalioctlothers">WdfIoTargetFormatRequestForInternalIoctlOthers</a> are completed.


### -field WdfRequestTypeUsb

The target device is a USB device. (This value is used only in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structures.)


### -field WdfRequestTypeNoFormat

The request object's type has not been specified.


### -field WdfRequestTypeMax

The maximum value that has been assigned to a valid IRP major function code.


## -remarks



The <b>WDF_REQUEST_TYPE</b> enumeration type is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structures.

For information about how a framework-based driver can handle request types that the framework does not support, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-an-irp-that-the-framework-does-not-support">Handling an IRP that the Framework Does Not Support</a>.

For the UMDF version of this enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE (UMDF)</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EvtDeviceFileCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcontrol/nc-wdfcontrol-evt_wdf_device_shutdown_notification">EvtDeviceShutdownNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_cleanup">EvtFileCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_file_close">EvtFileClose</a>
 

 

