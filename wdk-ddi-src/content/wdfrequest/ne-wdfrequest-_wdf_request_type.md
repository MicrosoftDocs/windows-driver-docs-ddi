---
UID: NE:wdfrequest._WDF_REQUEST_TYPE
title: "_WDF_REQUEST_TYPE"
author: windows-driver-content
description: The WDF_REQUEST_TYPE enumeration type identifies types of requests that a framework request object might contain.
old-location: wdf\wdf_request_type.htm
old-project: wdf
ms.assetid: 91c036a0-7fce-4c7d-a217-eb1c487a15d0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_43f31fe0-45c1-45d2-adcc-d0d931327eeb.xml, WDF_REQUEST_TYPE, WDF_REQUEST_TYPE enumeration, WdfRequestTypeCleanup, WdfRequestTypeClose, WdfRequestTypeCreate, WdfRequestTypeCreateMailSlot, WdfRequestTypeCreateNamedPipe, WdfRequestTypeDeviceChange, WdfRequestTypeDeviceControl, WdfRequestTypeDeviceControlInternal, WdfRequestTypeDirectoryControl, WdfRequestTypeFileSystemControl, WdfRequestTypeFlushBuffers, WdfRequestTypeLockControl, WdfRequestTypeMax, WdfRequestTypeNoFormat, WdfRequestTypeOther, WdfRequestTypePnp, WdfRequestTypePower, WdfRequestTypeQueryEA, WdfRequestTypeQueryInformation, WdfRequestTypeQueryQuota, WdfRequestTypeQuerySecurity, WdfRequestTypeQueryVolumeInformation, WdfRequestTypeRead, WdfRequestTypeSetEA, WdfRequestTypeSetInformation, WdfRequestTypeSetQuota, WdfRequestTypeSetSecurity, WdfRequestTypeSetVolumeInformation, WdfRequestTypeShutdown, WdfRequestTypeSystemControl, WdfRequestTypeUsb, WdfRequestTypeWrite, _WDF_REQUEST_TYPE, kmdf.wdf_request_type, wdf.wdf_request_type, wdfrequest/WDF_REQUEST_TYPE, wdfrequest/WdfRequestTypeCleanup, wdfrequest/WdfRequestTypeClose, wdfrequest/WdfRequestTypeCreate, wdfrequest/WdfRequestTypeCreateMailSlot, wdfrequest/WdfRequestTypeCreateNamedPipe, wdfrequest/WdfRequestTypeDeviceChange, wdfrequest/WdfRequestTypeDeviceControl, wdfrequest/WdfRequestTypeDeviceControlInternal, wdfrequest/WdfRequestTypeDirectoryControl, wdfrequest/WdfRequestTypeFileSystemControl, wdfrequest/WdfRequestTypeFlushBuffers, wdfrequest/WdfRequestTypeLockControl, wdfrequest/WdfRequestTypeMax, wdfrequest/WdfRequestTypeNoFormat, wdfrequest/WdfRequestTypeOther, wdfrequest/WdfRequestTypePnp, wdfrequest/WdfRequestTypePower, wdfrequest/WdfRequestTypeQueryEA, wdfrequest/WdfRequestTypeQueryInformation, wdfrequest/WdfRequestTypeQueryQuota, wdfrequest/WdfRequestTypeQuerySecurity, wdfrequest/WdfRequestTypeQueryVolumeInformation, wdfrequest/WdfRequestTypeRead, wdfrequest/WdfRequestTypeSetEA, wdfrequest/WdfRequestTypeSetInformation, wdfrequest/WdfRequestTypeSetQuota, wdfrequest/WdfRequestTypeSetSecurity, wdfrequest/WdfRequestTypeSetVolumeInformation, wdfrequest/WdfRequestTypeShutdown, wdfrequest/WdfRequestTypeSystemControl, wdfrequest/WdfRequestTypeUsb, wdfrequest/WdfRequestTypeWrite
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
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


## -enum-fields




### -field WdfRequestTypeCreate

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request. The framework delivers this type of request to a driver's <a href="https://msdn.microsoft.com/ee44c0bf-1fca-442d-8871-df6079e89ced">EvtDeviceFileCreate</a> callback function.


### -field WdfRequestTypeCreateNamedPipe

The request object represents an <b>IRP_MJ_CREATE_NAMED_PIPE</b> request. The framework does not handle this type of request.


### -field WdfRequestTypeClose

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request. The framework delivers this type of request to a driver's <a href="https://msdn.microsoft.com/8ddcb9cb-d184-4ec8-a321-599394a8512e">EvtFileClose</a> callback function.


### -field WdfRequestTypeRead

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeWrite

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeQueryInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeQueryEA

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetEA

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549346">IRP_MJ_SET_EA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeFlushBuffers

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeQueryVolumeInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetVolumeInformation

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeDirectoryControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeFileSystemControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeDeviceControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeDeviceControlInternal

The request object represents an  <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> request. The framework delivers this type of request to a driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


### -field WdfRequestTypeShutdown

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a> callback function, if it exists.


### -field WdfRequestTypeLockControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeCleanup

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a> request. The framework delivers this type of request to a driver's <a href="https://msdn.microsoft.com/8ce3d316-3976-4af5-a0ae-af4e93f380a1">EvtFileCleanup</a> callback function.


### -field WdfRequestTypeCreateMailSlot

The request object represents an <b>IRP_MJ_CREATE_MAILSLOT</b> request. The framework does not handle this type of request.


### -field WdfRequestTypeQuerySecurity

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549298">IRP_MJ_QUERY_SECURITY</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetSecurity

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549407">IRP_MJ_SET_SECURITY</a> request. The framework does not handle this type of request.


### -field WdfRequestTypePower

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">general</a>, <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">FDO</a>, and <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">PDO</a> callback functions for Plug and Play (PnP) and power management, if the callback functions exist.


### -field WdfRequestTypeSystemControl

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a> request. The framework handles this type of request for the driver, if the driver supports <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Windows Management Instrumentation (WMI)</a>.


### -field WdfRequestTypeDeviceChange

The request object represents an <b>IRP_MJ_DEVICE_CHANGE</b> request. The framework does not handle this type of request.


### -field WdfRequestTypeQueryQuota

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypeSetQuota

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a> request. The framework does not handle this type of request.


### -field WdfRequestTypePnp

The request object represents an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a> request. The framework handles this type of request for the driver, but the framework also calls the driver's <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">general</a>, <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">FDO</a>, and <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">PDO</a> callback functions for PnP and power management, if the callback functions exist.


### -field WdfRequestTypeOther

A driver receives this request type in its <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> event callback function when requests formatted with <a href="https://msdn.microsoft.com/library/windows/hardware/ff548599">WdfIoTargetFormatRequestForInternalIoctlOthers</a> are completed.


### -field WdfRequestTypeUsb

The target device is a USB device. (This value is used only in <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structures.)


### -field WdfRequestTypeNoFormat

The request object's type has not been specified.


### -field WdfRequestTypeMax

The maximum value that has been assigned to a valid IRP major function code.


## -remarks



The <b>WDF_REQUEST_TYPE</b> enumeration type is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structures.

For information about how a framework-based driver can handle request types that the framework does not support, see <a href="https://msdn.microsoft.com/0481f335-f63b-4f93-8eb4-523a70082302">Handling an IRP that the Framework Does Not Support</a>.

For the UMDF version of this enumeration, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561467">WDF_REQUEST_TYPE (UMDF)</a>.




## -see-also




<a href="https://msdn.microsoft.com/ee44c0bf-1fca-442d-8871-df6079e89ced">EvtDeviceFileCreate</a>



<a href="https://msdn.microsoft.com/365e669b-b4a1-432a-ab0c-9292a910256e">EvtDeviceShutdownNotification</a>



<a href="https://msdn.microsoft.com/8ce3d316-3976-4af5-a0ae-af4e93f380a1">EvtFileCleanup</a>



<a href="https://msdn.microsoft.com/8ddcb9cb-d184-4ec8-a321-599394a8512e">EvtFileClose</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

