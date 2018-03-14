---
UID: NC:dispmprt.DXGKDDI_SET_POWER_STATE
title: DXGKDDI_SET_POWER_STATE
author: windows-driver-content
description: The DxgkDdiSetPowerState function sets the power state of a display adapter or a child device of a display adapter.
old-location: display\dxgkddisetpowerstate.htm
old-project: display
ms.assetid: 6462be4f-1f6e-4b85-a3ba-15820ee8605b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_SET_POWER_STATE, DmFunctions_712dfd67-ab92-4ffb-80e8-18e6b80a0dd4.xml, DxgkDdiSetPowerState, DxgkDdiSetPowerState callback function [Display Devices], display.dxgkddisetpowerstate, dispmprt/DxgkDdiSetPowerState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkDdiSetPowerState
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_SET_POWER_STATE callback


## -description


The <i>DxgkDdiSetPowerState</i> function sets the power state of a display adapter or a child device of a display adapter.


## -prototype


````
DXGKDDI_SET_POWER_STATE DxgkDdiSetPowerState;

NTSTATUS DxgkDdiSetPowerState(
  _In_ const PVOID              MiniportDeviceContext,
  _In_       ULONG              DeviceUid,
  _In_       DEVICE_POWER_STATE DevicePowerState,
  _In_       POWER_ACTION       ActionType
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param DeviceUid [in]

A positive integer that identifies the device for which the power state is to be set. If <i>DeviceUid</i> is equal to <b>DISPLAY_ADAPTER_HW_ID</b> (defined in Video.h), the device is the display adapter itself. Otherwise, <i>DeviceUid</i> is the identifier of a child device of the display adapter. Child device identifiers were previously assigned by the <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function.


### -param DevicePowerState [in]

A <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> enumeration value that supplies the power state (<b>PowerDeviceD0</b>, <b>PowerDeviceD1</b>, <b>PowerDeviceD2</b>, <b>PowerDeviceD3</b>) to which the device should be set.


### -param ActionType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560459">POWER_ACTION</a> enumeration value that supplies the reason (<b>PowerActionSleep</b>, <b>PowerActionHibernate</b>, <b>PowerActionShutdown</b>) for the power state change.


## -returns



<i>DxgkDdiSetPowerState</i> returns <b>STATUS_SUCCESS</b> if it succeeds. <i>DxgkDdiSetPowerState</i> should never fail; however, it can return any NTSTATUS-typed value that is defined in <i>Ntstatus.h</i> and that passes the <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NT_SUCCESS(Status)</a> macro.




## -remarks



If the requested state is equal to <b>PowerDeviceD1</b>, <b>PowerDeviceD2</b>, or <b>PowerDeviceD3</b>, <i>DxgkDdiSetPowerState</i> saves any context that will later be required to bring the device back to <b>PowerDeviceD0</b> and then places the device in the requested state. If the requested state is <b>PowerDeviceD0</b> (fully on), <i>DxgkDdiSetPowerState</i> restores the device context and places the device in <b>PowerDeviceD0</b>.

If <i>DxgkDdiSetPowerState</i> is called with a request to put the VGA-enabled display adapter into hibernation, it should not power down the display adapter. Instead, it should save the context and let the bus driver power down the display adapter. That way, the power manager can display hibernation progress after the display miniport driver has been notified about the power state change.

The operating system might call <i>DxgkDdiSetPowerState</i> on a child device of the display adapter that is no longer connected (for example, a monitor that was recently unplugged). This anomaly occurs because an inherent latency exists between the time that the operating system calls the driver's <i>DxgkDdiSetPowerState</i> and the time that the operating system processes the disconnection. The driver must handle such situations without failing.

If <i>DevicePowerState</i> is equal to <b>PowerDeviceD0</b>, do not rely on the value of <i>ActionType</i>.

Starting with Windows Display Driver Model (WDDM) 1.2, if the <i>DevicePowerState</i> parameter is set to <b>PowerDeviceD0</b>, the display miniport driver should call <a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a> to query the information about the display mode. This display mode might have been been previously set by the firmware and system loader. If <b>DxgkCbAcquirePostDisplayOwnership</b> returns with <b>STATUS_SUCCESS</b>, the driver should determine whether it has to reinitialize the display based on the display mode information that was returned through the <i>DisplayInfo</i> parameter. Otherwise,  the driver should not assume that any specific display mode is currently enabled on the device, and it should initialize the display.

The <i>DxgkDdiSetPowerState</i> function should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



 

 


