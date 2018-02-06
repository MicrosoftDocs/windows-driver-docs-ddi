---
UID: NC:dispmprt.DXGKDDI_NOTIFY_ACPI_EVENT
title: DXGKDDI_NOTIFY_ACPI_EVENT
author: windows-driver-content
description: Notifies the display miniport driver about certain ACPI events.
old-location: display\dxgkddinotifyacpievent.htm
old-project: display
ms.assetid: fdefde51-0e90-4324-9c14-e8259fc872b3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddinotifyacpievent, DxgkDdiNotifyAcpiEvent callback function [Display Devices], DxgkDdiNotifyAcpiEvent, DXGKDDI_NOTIFY_ACPI_EVENT, DXGKDDI_NOTIFY_ACPI_EVENT, dispmprt/DxgkDdiNotifyAcpiEvent, DmFunctions_de0d32a9-a592-4fe2-86e1-66a436be5874.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiNotifyAcpiEvent
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKDDI_NOTIFY_ACPI_EVENT callback


## -description


Notifies the display miniport driver about certain ACPI events.


## -prototype


````
DXGKDDI_NOTIFY_ACPI_EVENT DxgkDdiNotifyAcpiEvent;

NTSTATUS DxgkDdiNotifyAcpiEvent(
  _In_  const PVOID           MiniportDeviceContext,
  _In_        DXGK_EVENT_TYPE EventType,
  _In_        ULONG           Event,
  _In_        PVOID           Argument,
  _Out_       PULONG          AcpiFlags
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that represents a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param EventType [in]

A <a href="..\dispmprt\ne-dispmprt-_dxgk_event_type.md">DXGK_EVENT_TYPE</a> enumerator that supplies the event type (<b>DpAcpiEvent</b>, <b>DpPowerStateEvent</b>, <b>DpDockingEvent</b>).


### -param Event [in]

The event number. The following table lists the possible event numbers for each of the event types.
<table>
<tr>
<th>Event type</th>
<th>Possible event numbers</th>
</tr>
<tr>
<td>
DpAcpiEvent

</td>
<td>
The following are the allowed events as defined in  Dispmprt.h:

<ul>
<li>ACPI_NOTIFY_CYCLE_DISPLAY_HOTKEY - It  notifies the operating system that the user has pressed the cycle display hotkey. </li>
<li>ACPI_NOTIFY_DOCK_EVENT - Indicates that a docking event has occurred. For example, the user docked or undocked a mobile computer.</li>
<li>ACPI_NOTIFY_DEVICE_HOTPLUG - Indicates that the status of any output device attached to the VGA controller has been changed. For example, the user removed or plugged a CRT display to the VGA port. </li>
<li>ACPI_NOTIFY_PANEL_SWITCH - Indicates that the status of one of the output devices attached to the VGA controller has been toggled. For example, the user switched the active output display from LCD to CRT display type.</li>
<li>ACPI_NOTIFY_VIDEO_WAKEUP - Indicates that the output display has been resumed. For example, the user has reactivated the computer display.</li>
</ul>
Defined in <i>Dispmprt.h</i>.

</td>
</tr>
<tr>
<td>
DpPowerStateEvent

</td>
<td>
PO_CB_LID_SWITCH_STATE, PO_CB_AC_STATUS

Defined in <i>Wdm.h</i>.

</td>
</tr>
<tr>
<td>
DpDockingEvent

</td>
<td>
ACPI_NOTIFY_DOCK_EVENT - Indicates that a docking event has occurred. For example, the user docked or undocked a mobile computer.

Defined in <i>Dispmprt.h</i>.

</td>
</tr>
</table> 


### -param Argument [in]

A pointer to an argument that depends on the event. For most events, this will be <b>NULL</b>. The following table shows the event arguments, which are ULONG values, for specified event numbers that are available.
<table>
<tr>
<th>Event number</th>
<th>Possible event arguments</th>
</tr>
<tr>
<td>
PO_CB_AC_STATUS

</td>
<td>
 0 - Indicates that the system is on battery power.

 1 - Indicates that the system is on AC power.

</td>
</tr>
<tr>
<td>
PO_CB_LID_SWITCH_STATE

</td>
<td>
 0 - Indicates that the lid is being closed.

 1 - Indicates that the lid is being opened. 

</td>
</tr>
</table> 


### -param AcpiFlags [out]

A pointer to a value that indicates the type of request that the display miniport driver should make to the operating system. The following table shows the values that can be specified.
<table>
<tr>
<th>Value</th>
<th>Request type</th>
</tr>
<tr>
<td>
DXGK_ACPI_CHANGE_DISPLAY_MODE

</td>
<td>
The display miniport driver makes a request to the operating system to call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function and then to initiate a mode change to the new recommended active video present network (VidPN). For example, the display miniport driver might make this request if the user has specified a mode change.

</td>
</tr>
<tr>
<td>
DXGK_ACPI_POLL_DISPLAY_CHILDREN

</td>
<td>
The display miniport driver makes a request to the operating system to poll the connectivity of the children of the display adapter represented by <i>MiniportDeviceContext</i>.

</td>
</tr>
</table> 

This parameter is ignored if this function returns an error or if the display adapter loses power. 


## -returns


<i>DxgkDdiNotifyAcpiEvent</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.



## -remarks


<i>DxgkDdiNotifyAcpiEvent</i> is an optional display miniport driver function.

<i>DxgkDdiNotifyAcpiEvent</i> should be made pageable.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkcb_eval_acpi_method.md">DxgkCbEvalAcpiMethod</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_NOTIFY_ACPI_EVENT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

