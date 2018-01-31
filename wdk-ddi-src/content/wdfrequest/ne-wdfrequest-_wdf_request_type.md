---
UID: NE:wdfrequest._WDF_REQUEST_TYPE
title: "_WDF_REQUEST_TYPE"
author: windows-driver-content
description: The WDF_REQUEST_TYPE enumeration type identifies types of requests that a framework request object might contain.
old-location: wdf\wdf_request_type.htm
old-project: wdf
ms.assetid: 91c036a0-7fce-4c7d-a217-eb1c487a15d0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestTypeCreateMailSlot, wdfrequest/WdfRequestTypeDeviceControl, wdfrequest/WdfRequestTypeShutdown, wdfrequest/WdfRequestTypeSystemControl, wdfrequest/WdfRequestTypeNoFormat, wdfrequest/WdfRequestTypePower, wdfrequest/WdfRequestTypeWrite, WdfRequestTypeDeviceControl, wdfrequest/WdfRequestTypeDeviceChange, WDF_REQUEST_TYPE, WdfRequestTypeFlushBuffers, WdfRequestTypeFileSystemControl, wdfrequest/WdfRequestTypePnp, WdfRequestTypeOther, wdfrequest/WdfRequestTypeSetQuota, wdfrequest/WdfRequestTypeLockControl, wdfrequest/WdfRequestTypeSetInformation, WdfRequestTypeQueryVolumeInformation, WdfRequestTypePnp, wdfrequest/WdfRequestTypeQueryVolumeInformation, wdfrequest/WDF_REQUEST_TYPE, wdfrequest/WdfRequestTypeFileSystemControl, WdfRequestTypeCreateNamedPipe, wdfrequest/WdfRequestTypeSetSecurity, wdfrequest/WdfRequestTypeRead, WdfRequestTypeSystemControl, kmdf.wdf_request_type, wdfrequest/WdfRequestTypeQueryQuota, WdfRequestTypeSetSecurity, WdfRequestTypeDeviceChange, wdfrequest/WdfRequestTypeQueryEA, _WDF_REQUEST_TYPE, wdfrequest/WdfRequestTypeOther, WdfRequestTypeSetQuota, wdfrequest/WdfRequestTypeDeviceControlInternal, wdfrequest/WdfRequestTypeCreateNamedPipe, wdfrequest/WdfRequestTypeMax, WdfRequestTypeUsb, WdfRequestTypeDeviceControlInternal, WdfRequestTypeWrite, wdfrequest/WdfRequestTypeFlushBuffers, wdfrequest/WdfRequestTypeClose, wdfrequest/WdfRequestTypeUsb, wdfrequest/WdfRequestTypeCleanup, wdf.wdf_request_type, WdfRequestTypeRead, WdfRequestTypeSetVolumeInformation, WdfRequestTypeNoFormat, WdfRequestTypeSetEA, WdfRequestTypePower, wdfrequest/WdfRequestTypeCreate, WdfRequestTypeQueryQuota, WdfRequestTypeDirectoryControl, WdfRequestTypeCreate, WdfRequestTypeQuerySecurity, WdfRequestTypeLockControl, wdfrequest/WdfRequestTypeDirectoryControl, WdfRequestTypeQueryInformation, wdfrequest/WdfRequestTypeSetEA, wdfrequest/WdfRequestTypeCreateMailSlot, DFRequestObjectRef_43f31fe0-45c1-45d2-adcc-d0d931327eeb.xml, WdfRequestTypeMax, WdfRequestTypeSetInformation, wdfrequest/WdfRequestTypeSetVolumeInformation, WdfRequestTypeCleanup, wdfrequest/WdfRequestTypeQuerySecurity, WdfRequestTypeShutdown, WdfRequestTypeQueryEA, WdfRequestTypeClose, WDF_REQUEST_TYPE enumeration, wdfrequest/WdfRequestTypeQueryInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# _WDF_REQUEST_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_TYPE</b> enumeration type identifies types of requests that a framework request object might contain.


## -syntax


````
typedef enum _WDF_REQUEST_TYPE { 
  WdfRequestTypeCreate                  = 0x0,
  WdfRequestTypeCreateNamedPipe         = 0x1,
  WdfRequestTypeClose                   = 0x2,
  WdfRequestTypeRead                    = 0x3,
  WdfRequestTypeWrite                   = 0x4,
  WdfRequestTypeQueryInformation        = 0x5,
  WdfRequestTypeSetInformation          = 0x6,
  WdfRequestTypeQueryEA                 = 0x7,
  WdfRequestTypeSetEA                   = 0x8,
  WdfRequestTypeFlushBuffers            = 0x9,
  WdfRequestTypeQueryVolumeInformation  = 0xa,
  WdfRequestTypeSetVolumeInformation    = 0xb,
  WdfRequestTypeDirectoryControl        = 0xc,
  WdfRequestTypeFileSystemControl       = 0xd,
  WdfRequestTypeDeviceControl           = 0xe,
  WdfRequestTypeDeviceControlInternal   = 0xf,
  WdfRequestTypeShutdown                = 0x10,
  WdfRequestTypeLockControl             = 0x11,
  WdfRequestTypeCleanup                 = 0x12,
  WdfRequestTypeCreateMailSlot          = 0x13,
  WdfRequestTypeQuerySecurity           = 0x14,
  WdfRequestTypeSetSecurity             = 0x15,
  WdfRequestTypePower                   = 0x16,
  WdfRequestTypeSystemControl           = 0x17,
  WdfRequestTypeDeviceChange            = 0x18,
  WdfRequestTypeQueryQuota              = 0x19,
  WdfRequestTypeSetQuota                = 0x1A,
  WdfRequestTypePnp                     = 0x1B,
  WdfRequestTypeOther                   = 0x1C,
  WdfRequestTypeUsb                     = 0x40,
  WdfRequestTypeNoFormat                = 0xFF,
  WdfRequestTypeMax                     = 0x100
} WDF_REQUEST_TYPE;
````


## -enum-fields




#### - WdfRequestTypeCreate

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request. The framework delivers this type of request to a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function.


#### - WdfRequestTypeCreateNamedPipe

The request object represents an <b>IRP_MJ_CREATE_NAMED_PIPE</b> request. The framework does not handle this type of request.


#### - WdfRequestTypeClose

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request. The framework delivers this type of request to a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EvtFileClose</a> callback function.


#### - WdfRequestTypeRead

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### - WdfRequestTypeWrite

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### - WdfRequestTypeQueryInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeSetInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeQueryEA

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeSetEA

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549346">IRP_MJ_SET_EA</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeFlushBuffers

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeQueryVolumeInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeSetVolumeInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeDirectoryControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeFileSystemControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeDeviceControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### - WdfRequestTypeDeviceControlInternal

The request object represents an  <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### - WdfRequestTypeShutdown

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a> callback function, if it exists.


#### - WdfRequestTypeLockControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeCleanup

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a> request. The framework delivers this type of request to a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a> callback function.


#### - WdfRequestTypeCreateMailSlot

The request object represents an <b>IRP_MJ_CREATE_MAILSLOT</b> request. The framework does not handle this type of request.


#### - WdfRequestTypeQuerySecurity

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549298">IRP_MJ_QUERY_SECURITY</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeSetSecurity

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549407">IRP_MJ_SET_SECURITY</a> request. The framework does not handle this type of request.


#### - WdfRequestTypePower

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">general</a>, <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">FDO</a>, and <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">PDO</a> callback functions for Plug and Play (PnP) and power management, if the callback functions exist.


#### - WdfRequestTypeSystemControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a> request. The framework handles this type of request for the driver, if the driver supports <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Windows Management Instrumentation (WMI)</a>.


#### - WdfRequestTypeDeviceChange

The request object represents an <b>IRP_MJ_DEVICE_CHANGE</b> request. The framework does not handle this type of request.


#### - WdfRequestTypeQueryQuota

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a> request. The framework does not handle this type of request.


#### - WdfRequestTypeSetQuota

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a> request. The framework does not handle this type of request.


#### - WdfRequestTypePnp

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">general</a>, <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">FDO</a>, and <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">PDO</a> callback functions for PnP and power management, if the callback functions exist.


#### - WdfRequestTypeOther

A driver receives this request type in its <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> event callback function when requests formatted with <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctlothers.md">WdfIoTargetFormatRequestForInternalIoctlOthers</a> are completed.


#### - WdfRequestTypeUsb

The target device is a USB device. (This value is used only in <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structures.)


#### - WdfRequestTypeNoFormat

The request object's type has not been specified.


#### - WdfRequestTypeMax

The maximum value that has been assigned to a valid IRP major function code.


## -remarks


The <b>WDF_REQUEST_TYPE</b> enumeration type is used in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> and <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structures.

For information about how a framework-based driver can handle request types that the framework does not support, see <a href="https://msdn.microsoft.com/0481f335-f63b-4f93-8eb4-523a70082302">Handling an IRP that the Framework Does Not Support</a>.

For the UMDF version of this enumeration, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE (UMDF)</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EvtFileClose</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a>

<a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

