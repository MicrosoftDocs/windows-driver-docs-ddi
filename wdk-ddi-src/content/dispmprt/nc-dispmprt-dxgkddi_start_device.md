---
UID: NC:dispmprt.DXGKDDI_START_DEVICE
title: DXGKDDI_START_DEVICE
author: windows-driver-content
description: The DxgkDdiStartDevice function prepares a display adapter to receive I/O requests.
old-location: display\dxgkddistartdevice.htm
old-project: display
ms.assetid: ffacbb39-2581-4207-841d-28ce57fbc64d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_START_DEVICE, DmFunctions_3b4ea5b7-9ccb-408f-9f37-693965ee99cf.xml, DxgkDdiStartDevice, DxgkDdiStartDevice callback function [Display Devices], display.dxgkddistartdevice, dispmprt/DxgkDdiStartDevice
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
-	dispmprt.h
api_name:
-	DxgkDdiStartDevice
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_START_DEVICE callback


## -description


The <i>DxgkDdiStartDevice</i> function prepares a display adapter to receive I/O requests.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param DxgkStartInfo [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562055">DXGK_START_INFO</a> structure that contains information that the display miniport driver needs for initialization. 


### -param DxgkInterface [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that contains pointers to functions, implemented by the DirectX graphics kernel subsystem, that the display miniport driver can call. 


### -param NumberOfVideoPresentSources [out]

A pointer to a <b>ULONG</b> variable that receives the number of video present sources supported by the display adapter. For more information about video present sources, see <a href="https://msdn.microsoft.com/27687fa4-1266-4341-b68a-83374c24ef73">Multiple Monitors and Video Present Networks</a>.


### -param NumberOfChildren [out]

A pointer to a <b>ULONG</b> variable that receives the total number of devices that are children of the display adapter represented by <i>MiniportDeviceContext</i>. This count must include potential child devices as well as child devices that are currently present. For example, if docking a portable computer will make additional video outputs available, those video outputs must be counted regardless of whether the portable computer is currently docked. For more information about child devices, see <a href="https://msdn.microsoft.com/9fd20e1a-db98-4571-8fc4-6d33fd0e2f16">Child Devices of the Display Adapter</a>.


## -returns



<i>DxgkDdiStartDevice</i> returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The <i>DxgkDdiStartDevice</i> function must perform the following actions:

<ul>
<li>
Save the function pointers supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure passed to the <i>DxgkInterface</i> parameter. Also save the <b>DeviceHandle</b> member of the <b>DXGKRNL_INTERFACE</b> structure; you will need that handle to call back into the DirectX graphics kernel subsystem.

</li>
<li>
Allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561053">DXGK_DEVICE_INFO</a> structure, and call <a href="https://msdn.microsoft.com/cb627eab-93b9-49c5-bd35-4a57220366e7">DxgkCbGetDeviceInformation</a> to fill in the members of that structure, which include the registry path, the PDO, and a list of translated resources for the display adapter represented by <i>MiniportDeviceContext</i>. Save selected members (ones that the display miniport driver will need later) of the <b>DXGK_DEVICE_INFO</b> structure in the context block represented by <i>MiniportDeviceContext.</i>

</li>
<li>
Map memory resources into system space by calling the <a href="https://msdn.microsoft.com/916a4d1d-0c40-4125-89ae-488251b04810">DxgkCbMapMemory</a> function.

</li>
<li>
Initialize the context block represented by <i>MiniportDeviceContext</i> with any state that is required to prepare the hardware to receive I/O requests.

</li>
<li>
Set <i>NumberOfVideoPresentSources </i> to the number of video present sources supported by the display adapter that is represented by <i>MiniportDeviceContext</i>.

</li>
<li>
Set <i>NumberOfChildren </i> to the number of devices that are (or could become) children of the display adapter represented by <i>MiniportDeviceContext</i>.

</li>
<li>
Enable interrupts for the display adapter represented by <i>MiniportDeviceContext</i>.

</li>
</ul>
Starting with Windows Display Driver Model (WDDM) 1.2, the display miniport driver calls   the <a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a> function to obtain the information about the display mode that had been previously set by the firmware and system loader. If <b>DxgkCbAcquirePostDisplayOwnership</b> returns with <b>STATUS_SUCCESS</b>, the driver determines whether it has to reinitialize the display based on the display mode information that was returned through the <i>DisplayInfo</i> parameter. Otherwise,  the driver should not assume that any specific display mode is currently enabled on the device, and it should initialize the display.

The <i>DxgkDdiStartDevice</i> function should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561053">DXGK_DEVICE_INFO</a>



<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



<a href="https://msdn.microsoft.com/cb627eab-93b9-49c5-bd35-4a57220366e7">DxgkCbGetDeviceInformation</a>



<a href="https://msdn.microsoft.com/916a4d1d-0c40-4125-89ae-488251b04810">DxgkCbMapMemory</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/3c17c7cf-9cfa-421d-a503-88726519fb6c">DxgkDdiStopDevice</a>
 

 

