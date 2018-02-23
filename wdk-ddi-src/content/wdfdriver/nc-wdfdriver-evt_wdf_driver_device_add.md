---
UID: NC:wdfdriver.EVT_WDF_DRIVER_DEVICE_ADD
title: EVT_WDF_DRIVER_DEVICE_ADD
author: windows-driver-content
description: A driver's EvtDriverDeviceAdd event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: wdf\evtdriverdeviceadd.htm
old-project: wdf
ms.assetid: b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.evtdriverdeviceadd, EvtDriverDeviceAdd callback function, EvtDriverDeviceAdd, EVT_WDF_DRIVER_DEVICE_ADD, EVT_WDF_DRIVER_DEVICE_ADD, wdfdriver/EvtDriverDeviceAdd, DFDriverObjectRef_9b5ff898-9b1b-4eb6-87f7-42bee5deab18.xml, kmdf.evtdriverdeviceadd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdriver.h
apiname:
-	EvtDriverDeviceAdd
product: Windows
targetos: Windows
req.typenames: "*PWDF_DPC_CONFIG, WDF_DPC_CONFIG"
req.product: Windows 10 or later.
---

# EVT_WDF_DRIVER_DEVICE_ADD callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDriverDeviceAdd</i> event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.


## -prototype


````
EVT_WDF_DRIVER_DEVICE_ADD EvtDriverDeviceAdd;

NTSTATUS EvtDriverDeviceAdd(
  _In_    WDFDRIVER       Driver,
  _Inout_ PWDFDEVICE_INIT DeviceInit
)
{ ... }
````


## -parameters




### -param Driver [in]

A handle to a framework driver object that represents the driver.


### -param DeviceInit [in, out]

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


## -returns



The<i>EvtDriverDeviceAdd</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this callback function must return one of the error status values that are defined in <i>Ntstatus.h</i>. For more information, see the following Remarks section.




## -remarks



Each framework-based driver that supports PnP devices must provide the <i>EvtDriverDeviceAdd</i> callback function. The driver must place the callback function's address in its <a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a> structure before calling <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>.

The framework calls your driver's <i>EvtDriverDeviceAdd</i> callback function after a bus driver detects a device that has a hardware identifier (ID) that matches a hardware ID that your driver supports. You specify the hardware IDs that your driver supports by providing an INF file, which the operating system uses to install drivers the first time that one of your devices is connected to the computer. For more information about how the system uses INF files and hardware IDs, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/how-setup-selects-drivers">How Setup Selects Drivers</a>.

A driver's <i>EvtDriverDeviceAdd</i> callback function typically performs at least some of the following initialization operations:

<ul>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Create a framework device object</a> to represent the device.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Create I/O queues</a> so the driver can receive I/O requests.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces">Create device interfaces</a> that applications use to communicate with the device.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Create driver-defined interfaces</a> that other drivers can use.

</li>
<li>
Initialize <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-wmi-in-kmdf-drivers">Windows Management Instrumentation (WMI)</a> support.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-an-interrupt-object">Create interrupt objects</a>, if the driver handles device interrupts.

</li>
<li>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enable direct memory access (DMA) transactions</a>, if the driver handles DMA operations.

</li>
</ul>
Some drivers, especially filter drivers, might not create device objects for some devices. If an <i>EvtDriverDeviceAdd</i> callback function does not create a device object, it must still return STATUS_SUCCESS unless an error was encountered.

If a driver's <i>EvtDriverDeviceAdd</i> callback function creates a device object but does not return STATUS_SUCCESS, the framework deletes the device object and its child devices.

If a function driver's <i>EvtDriverDeviceAdd</i> callback function does not return STATUS_SUCCESS, the I/O manager does not build a device stack for the device.

If a filter driver's <i>EvtDriverDeviceAdd</i> callback function does not return STATUS_SUCCESS, the framework converts the return value to STATUS_SUCCESS, and the I/O manager builds the device stack without the filter driver.


#### Examples

To define an <i>EvtDriverDeviceAdd</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDriverDeviceAdd</i> callback function that is named <i>MyDriverDeviceAdd</i>, use the <b>EVT_WDF_DRIVER_DEVICE_ADD</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DRIVER_DEVICE_ADD MyDriverDeviceAdd;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS 
 MyDriverDeviceAdd (
    WDFDRIVER Driver,
    PWDFDEVICE_INIT DeviceInit
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DRIVER_DEVICE_ADD</b> function type is defined in the WdfDriver.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DRIVER_DEVICE_ADD</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>





<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="..\wdfdriver\ns-wdfdriver-_wdf_driver_config.md">WDF_DRIVER_CONFIG</a>





 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DRIVER_DEVICE_ADD callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

