---
UID: NC:dispmprt.DXGKDDI_NOTIFY_ACPI_EVENT
title: DXGKDDI_NOTIFY_ACPI_EVENT (dispmprt.h)
description: Notifies the display miniport driver about certain ACPI events.
old-location: display\dxgkddinotifyacpievent.htm
tech.root: display
ms.assetid: fdefde51-0e90-4324-9c14-e8259fc872b3
ms.date: 04/16/2018
ms.keywords: DXGKDDI_NOTIFY_ACPI_EVENT, DXGKDDI_NOTIFY_ACPI_EVENT callback, DmFunctions_de0d32a9-a592-4fe2-86e1-66a436be5874.xml, DxgkDdiNotifyAcpiEvent, DxgkDdiNotifyAcpiEvent callback function [Display Devices], display.dxgkddinotifyacpievent, dispmprt/DxgkDdiNotifyAcpiEvent
ms.topic: callback
req.header: dispmprt.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	dispmprt.h
api_name:
-	DxgkDdiNotifyAcpiEvent
product:
- Windows
targetos: Windows
req.typenames:
---

# DXGKDDI_NOTIFY_ACPI_EVENT callback function


## -description


Notifies the display miniport driver about certain ACPI events.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that represents a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param EventType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561067">DXGK_EVENT_TYPE</a> enumerator that supplies the event type (<b>DpAcpiEvent</b>, <b>DpPowerStateEvent</b>, <b>DpDockingEvent</b>).


### -param Event [in]

The event number. The following table lists the possible event numbers for each of the event types.

|Event type|Possible event numbers|
|--- |--- |
|DpAcpiEvent|The following are the allowed events as defined in  Dispmprt.h:<ul><li>ACPI_NOTIFY_CYCLE_DISPLAY_HOTKEY - It  notifies the operating system that the user has pressed the cycle display hotkey. </li><li>ACPI_NOTIFY_DOCK_EVENT - Indicates that a docking event has occurred. For example, the user docked or undocked a mobile computer.</li><li>ACPI_NOTIFY_DEVICE_HOTPLUG - Indicates that the status of any output device attached to the VGA controller has been changed. For example, the user removed or plugged a CRT display to the VGA port. </li><li>ACPI_NOTIFY_PANEL_SWITCH - Indicates that the status of one of the output devices attached to the VGA controller has been toggled. For example, the user switched the active output display from LCD to CRT display type.</li><li>ACPI_NOTIFY_VIDEO_WAKEUP - Indicates that the output display has been resumed. For example, the user has reactivated the computer display.</li></ul>|
|DpPowerStateEvent|PO_CB_LID_SWITCH_STATE, PO_CB_AC_STATUS<br/>Defined in Wdm.h.|
|DpDockingEvent|ACPI_NOTIFY_DOCK_EVENT - Indicates that a docking event has occurred. For example, the user docked or undocked a mobile computer.<br/>Defined in Dispmprt.h.|

### -param Argument [in]

A pointer to an argument that depends on the event. For most events, this will be <b>NULL</b>. The following table shows the event arguments, which are ULONG values, for specified event numbers that are available.

|Event number|Possible event arguments|
|--- |--- |
|PO_CB_AC_STATUS|0 - Indicates that the system is on battery power.<br/>1 - Indicates that the system is on AC power.|
|PO_CB_LID_SWITCH_STATE|0 - Indicates that the lid is being closed.<br/>1 - Indicates that the lid is being opened.|
 


### -param AcpiFlags [out]

A pointer to a value that indicates the type of request that the display miniport driver should make to the operating system. The following table shows the values that can be specified.

| **Value** | **Request type** | 
|:--|:--|
| DXGK_ACPI_CHANGE_DISPLAY_MODE | The display miniport driver makes a request to the operating system to call the [DxgkDdiRecommendFunctionalVidPn](https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b)  function and then to initiate a mode change to the new recommended active video present network (VidPN). For example, the display miniport driver might make this request if the user has specified a mode change. | 
| DXGK_ACPI_CHANGE_DISPLAY_TOPOLOGY |  | 
| DXGK_ACPI_POLL_DISPLAY_CHILDREN | The display miniport driver makes a request to the operating system to poll the connectivity of the children of the display adapter represented by MiniportDeviceContext. | 
| DXGK_ACPI_CHAIN_NOT_HANDLED | Indicates that an event with type DxgkChainedAcpiEvent was not handled by the hybrid discrete driver and should therefore be sent to the hybrid integrated driver. | 


This parameter is ignored if this function returns an error or if the display adapter loses power.


## -returns



<i>DxgkDdiNotifyAcpiEvent</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



<i>DxgkDdiNotifyAcpiEvent</i> is an optional display miniport driver function.

<i>DxgkDdiNotifyAcpiEvent</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/ce54cf4e-5b50-4142-b3c7-ff29b7bdbb35">DxgkCbEvalAcpiMethod</a>
 

 

