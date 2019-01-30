---
UID: NC:dispmprt.DXGKCB_INDICATE_CHILD_STATUS
title: DXGKCB_INDICATE_CHILD_STATUS (dispmprt.h)
description: The DxgkCbIndicateChildStatus function records the current status of a specified child device of a display adapter.
old-location: display\dxgkcbindicatechildstatus.htm
tech.root: display
ms.assetid: 780a8867-bba1-4b1b-a941-b55bfe087b7b
ms.date: 05/10/2018
ms.keywords: DXGKCB_INDICATE_CHILD_STATUS, DXGKCB_INDICATE_CHILD_STATUS callback, DpFunctions_db80be21-a515-411f-beb0-64f7514c11f4.xml, DxgkCbIndicateChildStatus, DxgkCbIndicateChildStatus callback function [Display Devices], display.dxgkcbindicatechildstatus, dispmprt/DxgkCbIndicateChildStatus
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbIndicateChildStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_INDICATE_CHILD_STATUS callback function


## -description


The <b>DxgkCbIndicateChildStatus</b> function records the current status of a specified child device of a display adapter.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


### -param ChildStatus [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561010">DXGK_CHILD_STATUS</a> structure that identifies the child device and describes the current status of the child device.


## -returns



<b>DxgkCbIndicateChildStatus</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The display miniport driver's DPC for ISR calls <b>DxgkCbIndicateChildStatus</b> when the display adapter generates an interrupt for any of the following reasons:

<ul>
<li>
An external device (typically a monitor) has been connected to one of the display adapter's child devices that has an HPD awareness value of <b>HpdAwarenessInterruptible</b>. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>TRUE</b>.

</li>
<li>
An external device (typically a monitor) has been disconnected from one of the display adapter's child devices that has an HPD awareness value of <b>HpdAwarenessInterruptible</b>. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>FALSE</b>.

</li>
<li>
The display device connected to one of its on-board child devices (that has a monitor orientation awareness value of <b>D3DKMDT_MOA_INTERRUPTIBLE</b>) has been rotated. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusRotation</b> and sets<i> ChildStatus</i>.<b>Rotation</b>.<b>Angle</b> to the angle of rotation.

</li>
</ul>
The display miniport driver's <a href="https://msdn.microsoft.com/fdefde51-0e90-4324-9c14-e8259fc872b3">DxgkDdiNotifyAcpiEvent</a> function calls <b>DxgkCbIndicateChildStatus</b> in the following situations:

<ul>
<li>
The lid on a portable computer gets opened. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>TRUE</b>.

</li>
<li>
The lid on a portable computer gets closed. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>FALSE</b>.

</li>
</ul>

#### Examples

The following code example shows how to record the current status of a child device.

```cpp
NTSTATUS
AtiSimulateMonitor(HW_DEVICE_EXTENSION *pHwDeviceExtension, PR2_SIMULATE_MONITOR i_pEscape)
{
    NTSTATUS Status;
    PVOID MonitorDescriptor = NULL;
    DXGK_CHILD_STATUS     ChildStatus;
    ChildStatus.ChildUid    =  pHwDeviceExtension-&gt;ulNumberDisplays | HW_ID_DISPLAY_CHILD;
    ChildStatus.Type    = StatusConnection;

    if(i_pEscape-&gt;Data == NULL) {
        // Remove a simulated monitor
        if(pHwDeviceExtension-&gt;pvSimulatedMonitorDescriptor != NULL) {
            ExFreePoolWithTag(pHwDeviceExtension-&gt;pvSimulatedMonitorDescriptor, ATI_TAG);
            pHwDeviceExtension-&gt;pvSimulatedMonitorDescriptor = NULL;
            pHwDeviceExtension-&gt;ulSimulatedMonitorDescriptorLength = 0;
           pHwDeviceExtension-&gt;ulRetryCount = 0;
           pHwDeviceExtension-&gt;bReportDescriptor = FALSE;

            ChildStatus.HotPlug.Connected = FALSE;
            Status = DxgkCbIndicateChildStatus(pHwDeviceExtension-&gt;DeviceHandle, &amp;ChildStatus);
        }
        else {
            // No simulated monitor is present so the request to remove one is invalid
            return STATUS_INVALID_PARAMETER;
        }
    }
    else {
        //Add a simulated monitor
    }
    return Status;
}
```


## -see-also




<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>



<a href="https://msdn.microsoft.com/478e0c52-4324-4062-8e1e-381808b0f481">DxgkDdiQueryChildStatus</a>
 

 

