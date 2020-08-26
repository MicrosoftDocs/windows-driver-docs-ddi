---
UID: NF:wdfinterrupt.WdfInterruptCreate
title: WdfInterruptCreate function (wdfinterrupt.h)
description: The WdfInterruptCreate method creates a framework interrupt object.
old-location: wdf\wdfinterruptcreate.htm
tech.root: wdf
ms.assetid: 6279f9ed-f271-45e6-92ef-2a919f3584ed
ms.date: 02/26/2018
keywords: ["WdfInterruptCreate function"]
ms.keywords: DFInterruptObjectRef_44b197bb-82d6-45ff-a640-67fd1de506cc.xml, WdfInterruptCreate, WdfInterruptCreate method, kmdf.wdfinterruptcreate, wdf.wdfinterruptcreate, wdfinterrupt/WdfInterruptCreate
f1_keywords:
 - "wdfinterrupt/WdfInterruptCreate"
 - "WdfInterruptCreate"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfInterruptCreate
targetos: Windows
req.typenames: 
---

# WdfInterruptCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptCreate</b> method creates a framework interrupt object.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param Configuration 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure that was initialized by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a>.


### -param Attributes 
[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework interrupt object.  (See Remarks for additional information.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Interrupt 
[out]
A pointer to a location that receives a handle to the new interrupt object.


## -returns



<b>WdfInterruptCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the WDF_INTERRUPT_CONFIG structure is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a> was called after the device was started.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a> also returns this value if the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EVT_WDF_DEVICE_PREPARE_HARDWARE</a> callback routine calls <b>WdfInterruptCreate</b> with   the <b>InterruptRaw</b> and <b>InterruptTranslated</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_PARENT_ASSIGNMENT_NOT_ALLOWED</b></dt>
</dl>
</td>
<td width="60%">
In KMDF version 1.9 or earlier, the driver specified a non-<b>NULL</b> value for the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure.

In KMDF version 1.11 or later, the driver specified a value other than a framework device or queue for the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The <b>AutomaticSerialization</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure is set to <b>TRUE</b> and either:

<ul>
<li>The execution level of the interrupt's parent object is <b>WdfExecutionLevelPassive</b> and the driver has supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>.</li>
<li>  The execution level of the interrupt's parent object is <b>WdfExecutionLevelDispatch</b> and the driver has supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a>.</li>
</ul>
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The driver requested passive-level interrupt handling on a platform earlier than Windows 8.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfInterruptCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers typically call the  <b>WdfInterruptCreate</b> method from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. Starting in KMDF version 1.11 and UMDF version 2.0, drivers can call <b>WdfInterruptCreate</b> from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDriverDeviceAdd</i>, the <b>InterruptRaw</b>  and <b>InterruptTranslated</b>  members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure
must be NULL. If the driver calls <b>WdfInterruptCreate</b> from <i>EvtDevicePrepareHardware</i>, these members must both be valid.

If you are creating a wake-capable interrupt object, as described in <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-an-interrupt-to-wake-a-device">Using an Interrupt to Wake a Device</a>, you must call <b>WdfInterruptCreate</b> from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>.

 Your driver must call <b>WdfInterruptCreate</b> once for each interrupt vector that its device requires. If the device supports message-signaled interrupts (MSI), the driver must create an interrupt object for each message that the device can support.

After the PnP manager assigns system resources to the device, the framework stores information about the device's assigned interrupt resources in the interrupt objects that the driver has created. (Drivers that <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-kernel-mode-driver-framework-with-non-pnp-drivers">do not support Plug and Play</a> cannot use interrupt objects.)

The system might not assign all of the interrupt resources that a device can support. For example, a driver would create eight interrupt objects for a device that is capable of supporting eight MSI messages. However, the system might assign only one message to the device. In that case, seven of the interrupt objects will be unused.

Typically, your driver should store interrupt-specific information, such as the copied contents of device interrupt registers, in the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that the driver passes to <b>WdfInterruptCreate</b> should describe the context space.

For drivers using framework version 1.9 and earlier, the parent of each interrupt object is the device object that the interrupt belongs to. The driver cannot change this parent, and the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>. Beginning in version 1.11, <b>ParentObject</b> can be a framework device object or queue object. If the driver specifies a parent, the driver must set the <b>AutomaticSerialization</b> member of the configuration structure to TRUE. The driver can specify a parent for both interrupts at DIRQL and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupts</a>.

If your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the framework interrupt object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure and a WDF_OBJECT_ATTRIBUTES structure and then calls <b>WdfInterruptCreate</b>.

```cpp
NTSTATUS  status;
WDF_INTERRUPT_CONFIG  interruptConfig;
WDF_OBJECT_ATTRIBUTES  interruptAttributes;

WDF_INTERRUPT_CONFIG_INIT(
                          &interruptConfig,
                          MyEvtInterruptIsr,
                          MyEvtInterruptDpc
                          );
WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &interruptAttributes,
                                        INTERRUPT_DATA
                                        );
status = WdfInterruptCreate(
                            device,
                            &interruptConfig,
                            &interruptAttributes,
                            &devExt->WdfInterrupt
                            );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_config_init">WDF_INTERRUPT_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdf-object-attributes-init-context-type">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>
 

 

