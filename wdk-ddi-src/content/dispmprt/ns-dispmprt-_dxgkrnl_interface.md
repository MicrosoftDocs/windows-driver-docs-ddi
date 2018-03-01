---
UID: NS:dispmprt._DXGKRNL_INTERFACE
title: "_DXGKRNL_INTERFACE"
author: windows-driver-content
description: The DXGKRNL_INTERFACE structure contains a handle to a display adapter and a set of function pointers.
old-location: display\dxgkrnl_interface2.htm
old-project: display
ms.assetid: d97d3ec6-aaa5-4f4a-a39f-42c09473b18e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDXGKRNL_INTERFACE, DXGKDDI_INTERFACE_VERSION_VISTA, DXGKDDI_INTERFACE_VERSION_VISTA_SP1, DXGKDDI_INTERFACE_VERSION_VISTA_WIN7, DXGKDDI_INTERFACE_VERSION_WIN8, DXGKRNL_INTERFACE, DXGKRNL_INTERFACE structure [Display Devices], DmStructs_86ab8b5f-f30b-4ad3-ac4d-34fc3a864f27.xml, PDXGKRNL_INTERFACE, PDXGKRNL_INTERFACE structure pointer [Display Devices], _DXGKRNL_INTERFACE, display.dxgkrnl_interface2, dispmprt/DXGKRNL_INTERFACE, dispmprt/PDXGKRNL_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available beginning with Windows Vista.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGKRNL_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGKRNL_INTERFACE, *PDXGKRNL_INTERFACE
---

# _DXGKRNL_INTERFACE structure


## -description


The <b>DXGKRNL_INTERFACE</b> structure contains a handle to a display adapter and  a set of function pointers. The functions are implemented by the display port driver and called by the display miniport driver. The display port driver provides the display miniport driver with the handle and function pointers by passing a <b>DXGKRNL_INTERFACE</b> structure to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


## -syntax


````
typedef struct _DXGKRNL_INTERFACE {
  ULONG                                 Size;
  ULONG                                 Version;
  HANDLE                                DeviceHandle;
  DXGKCB_EVAL_ACPI_METHOD               DxgkCbEvalAcpiMethod;
  DXGKCB_GET_DEVICE_INFORMATION         DxgkCbGetDeviceInformation;
  DXGKCB_INDICATE_CHILD_STATUS          DxgkCbIndicateChildStatus;
  DXGKCB_MAP_MEMORY                     DxgkCbMapMemory;
  DXGKCB_QUEUE_DPC                      DxgkCbQueueDpc;
  DXGKCB_QUERY_SERVICES                 DxgkCbQueryServices;
  DXGKCB_READ_DEVICE_SPACE              DxgkCbReadDeviceSpace;
  DXGKCB_SYNCHRONIZE_EXECUTION          DxgkCbSynchronizeExecution;
  DXGKCB_UNMAP_MEMORY                   DxgkCbUnmapMemory;
  DXGKCB_WRITE_DEVICE_SPACE             DxgkCbWriteDeviceSpace;
  DXGKCB_IS_DEVICE_PRESENT              DxgkCbIsDevicePresent;
  DXGKCB_GETHANDLEDATA                  DxgkCbGetHandleData;
  DXGKCB_GETHANDLEPARENT                DxgkCbGetHandleParent;
  DXGKCB_ENUMHANDLECHILDREN             DxgkCbEnumHandleChildren;
  DXGKCB_NOTIFY_INTERRUPT               DxgkCbNotifyInterrupt;
  DXGKCB_NOTIFY_DPC                     DxgkCbNotifyDpc;
  DXGKCB_QUERYVIDPNINTERFACE            DxgkCbQueryVidPnInterface;
  DXGKCB_QUERYMONITORINTERFACE          DxgkCbQueryMonitorInterface;
  DXGKCB_GETCAPTUREADDRESS              DxgkCbGetCaptureAddress;
  DXGKCB_LOG_ETW_EVENT                  DxgkCbLogEtwEvent;
  DXGKCB_EXCLUDE_ADAPTER_ACCESS         DxgkCbExcludeAdapterAccess;
#if DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  DXGKCB_CREATECONTEXTALLOCATION        DxgkCbCreateContextAllocation;
  DXGKCB_DESTROYCONTEXTALLOCATION       DxgkCbDestroyContextAllocation;
  DXGKCB_SETPOWERCOMPONENTACTIVE        DxgkCbSetPowerComponentActive;
  DXGKCB_SETPOWERCOMPONENTIDLE          DxgkCbSetPowerComponentIdle;
  DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP DxgkCbAcquirePostDisplayOwnership;
  DXGKCB_POWERRUNTIMECONTROLREQUEST     DxgkCbPowerRuntimeControlRequest;
  DXGKCB_SETPOWERCOMPONENTLATENCY       DxgkCbSetPowerComponentLatency;
  DXGKCB_SETPOWERCOMPONENTRESIDENCY     DxgkCbSetPowerComponentResidency;
  DXGKCB_COMPLETEFSTATETRANSITION       DxgkCbCompleteFStateTransition;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_M1)
  DXGKCB_COMPLETEPSTATETRANSITION       DxgkCbCompletePStateTransition;
#endif 
} DXGKRNL_INTERFACE, *PDXGKRNL_INTERFACE;
````


## -struct-fields




### -field Size

An integer that indicates the size, in bytes, of this structure.


### -field Version

A positive integer that indicates the version of the functional interface implemented by the display port driver.


The following are the allowed values, which are defined in D3dukmdt.h.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_VISTA"></a><a id="dxgkddi_interface_version_vista"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_VISTA</b></dt>
</dl>
</td>
<td width="60%">
Windows Vista

</td>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_VISTA_SP1"></a><a id="dxgkddi_interface_version_vista_sp1"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_VISTA_SP1</b></dt>
</dl>
</td>
<td width="60%">
Windows Vista with SP1

</td>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_VISTA_WIN7"></a><a id="dxgkddi_interface_version_vista_win7"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_VISTA_WIN7</b></dt>
</dl>
</td>
<td width="60%">
Windows 7

</td>
</tr>
<tr>
<td width="40%"><a id="DXGKDDI_INTERFACE_VERSION_WIN8"></a><a id="dxgkddi_interface_version_win8"></a><dl>
<dt><b>DXGKDDI_INTERFACE_VERSION_WIN8</b></dt>
</dl>
</td>
<td width="60%">
Windows 8

</td>
</tr>
</table>
 


### -field DeviceHandle

A handle, generated by the display port driver, that represents a display adapter. The display miniport driver passes the handle as an argument each time it calls any of the functions in DXGKRNL_INTERFACE.


### -field DxgkCbEvalAcpiMethod

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_eval_acpi_method.md">DxgkCbEvalAcpiMethod</a> function.


### -field DxgkCbGetDeviceInformation

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_get_device_information.md">DxgkCbGetDeviceInformation</a> function.


### -field DxgkCbIndicateChildStatus

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_indicate_child_status.md">DxgkCbIndicateChildStatus</a> function.


### -field DxgkCbMapMemory

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_map_memory.md">DxgkCbMapMemory</a> function.


### -field DxgkCbQueueDpc

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a> function.


### -field DxgkCbQueryServices

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a> function.


### -field DxgkCbReadDeviceSpace

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_read_device_space.md">DxgkCbReadDeviceSpace</a> function.


### -field DxgkCbSynchronizeExecution

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_synchronize_execution.md">DxgkCbSynchronizeExecution</a> function.


### -field DxgkCbUnmapMemory

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_unmap_memory.md">DxgkCbUnmapMemory</a> function.


### -field DxgkCbWriteDeviceSpace

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_write_device_space.md">DxgkCbWriteDeviceSpace</a> function.


### -field DxgkCbIsDevicePresent

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_is_device_present.md">DxgkCbIsDevicePresent</a> function.


### -field DxgkCbGetHandleData

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a> function.


### -field DxgkCbGetHandleParent

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandleparent.md">DxgkCbGetHandleParent</a> function.


### -field DxgkCbEnumHandleChildren

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_enumhandlechildren.md">DxgkCbEnumHandleChildren</a> function.


### -field DxgkCbNotifyInterrupt

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function.


### -field DxgkCbNotifyDpc

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a> function.


### -field DxgkCbQueryVidPnInterface

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_queryvidpninterface.md">DxgkCbQueryVidPnInterface</a> function.


### -field DxgkCbQueryMonitorInterface

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_querymonitorinterface.md">DxgkCbQueryMonitorInterface</a> function.


### -field DxgkCbGetCaptureAddress

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_getcaptureaddress.md">DxgkCbGetCaptureAddress</a> function.


### -field DxgkCbLogEtwEvent

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_log_etw_event.md">DxgkCbLogEtwEvent</a> function.


### -field DxgkCbExcludeAdapterAccess

A pointer to the display port driver's <a href="..\dispmprt\nc-dispmprt-dxgkcb_exclude_adapter_access.md">DxgkCbExcludeAdapterAccess</a> function.


### -field DxgkCbCreateContextAllocation

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a> function.

Supported starting with Windows 8.


### -field DxgkCbDestroyContextAllocation

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_destroycontextallocation.md">DxgkCbDestroyContextAllocation</a> function.

Supported starting with Windows 8.


### -field DxgkCbSetPowerComponentActive

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a> function.

Supported starting with Windows 8.


### -field DxgkCbSetPowerComponentIdle

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentidle.md">DxgkCbSetPowerComponentIdle</a> function.

Supported starting with Windows 8.


### -field DxgkCbAcquirePostDisplayOwnership

A pointer to the display port driver's <a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a> function.

Supported starting with Windows 8.


### -field DxgkCbPowerRuntimeControlRequest

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_powerruntimecontrolrequest.md">DxgkCbPowerRuntimeControlRequest</a> function.

Supported starting with Windows 8.


### -field DxgkCbSetPowerComponentLatency

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentlatency.md">DxgkCbSetPowerComponentLatency</a> function.

Supported starting with Windows 8.


### -field DxgkCbSetPowerComponentResidency

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentresidency.md">DxgkCbSetPowerComponentResidency</a> function.

Supported starting with Windows 8.


### -field DxgkCbCompleteFStateTransition

A pointer to the display port driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_completefstatetransition.md">DxgkCbCompleteFStateTransition</a> function.

Supported starting with Windows 8.


### -field DxgkCbCompletePStateTransition

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.


### -field DxgkCbMapContextAllocation

 


### -field DxgkCbUpdateContextAllocation

 


### -field DxgkCbReserveGpuVirtualAddressRange

 


### -field DxgkCbAcquireHandleData

 


### -field DxgkCbReleaseHandleData

 


### -field DxgkCbHardwareContentProtectionTeardown

 


### -field DxgkCbMultiPlaneOverlayDisabled

 


### -field DxgkCbMitigatedRangeUpdate

 


### -field DxgkCbInvalidateHwContext

 


### -field DxgkCbIndicateConnectorChange

 


### -field DxgkCbUnblockUEFIFrameBufferRanges

 


### -field DxgkCbAcquirePostDisplayOwnership2

 


### -field DxgkCbSetProtectedSessionStatus

 




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560940">Dxgkrnl Interface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKRNL_INTERFACE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

