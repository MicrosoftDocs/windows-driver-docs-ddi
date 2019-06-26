---
UID: NF:portcls.PcAddAdapterDevice
title: PcAddAdapterDevice function (portcls.h)
description: The PcAddAdapterDevice function adds an adapter device to the WDM device stack.
old-location: audio\pcaddadapterdevice.htm
tech.root: audio
ms.assetid: fa571ca0-194c-4018-9b93-a3cc687f7632
ms.date: 05/08/2018
ms.keywords: PcAddAdapterDevice, PcAddAdapterDevice function [Audio Devices], audio.pcaddadapterdevice, audpc-routines_5b2b0ba0-67b7-4c8d-bd47-b7e664500637.xml, portcls/PcAddAdapterDevice
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows 2000.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcAddAdapterDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcAddAdapterDevice function


## -description


The <b>PcAddAdapterDevice</b> function adds an adapter device to the WDM device stack.


## -parameters




### -param DriverObject [in]

Pointer to the driver object. This pointer is passed as a parameter to the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_add_device">AddDevice</a> handler. The driver object is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>.


### -param PhysicalDeviceObject [in]

Pointer to the device's <a href="https://docs.microsoft.com/windows-hardware/drivers/">physical device object (PDO)</a>. PortCls passes this pointer as a call parameter to the adapter's <i>AddDevice</i> handler. The PDO is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param StartDevice [in]

Pointer to the function that the operating system calls in order to start the device. For more information, see the following <b>Remarks</b> section.


### -param MaxObjects [in]

Specifies the maximum number of subdevices to be registered by calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>. This count sets the upper limit to the total number of miniport objects that the adapter driver can instantiate.


### -param DeviceExtensionSize [in]

Specifies the device extension size. Use zero for default size. See the following <b>Remarks</b> section for user-supplied extension sizes.


## -returns



<b>PcAddAdapterDevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



This function does most of the work that the audio adapter driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_add_device">AddDevice</a> handler needs to perform. <b>PcAddAdapterDevice</b> creates the device object, initializes the device context, and attaches the device object to the device stack.

An adapter driver calls <b>PcAddAdapterDevice</b> when it receives a call to its <i>AddDevice </i>handler. The adapter driver typically installs the <i>AddDevice </i>handler by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcinitializeadapterdriver">PcInitializeAdapterDriver</a>, although the driver can also install the handler by other means. <b>PcAddAdapterDevice</b> creates the <a href="https://docs.microsoft.com/windows-hardware/drivers/">functional device object (FDO)</a> for the PDO that was passed to the <i>AddDevice</i> handler.

<i>DeviceExtensionSize</i> is typically zero. Some adapter drivers might need to reserve additional space in the device extension, in which case they should specify a <i>DeviceExtensionSize</i> greater than PORT_CLASS_DEVICE_EXTENSION_SIZE, which is the default size. Any value greater than zero and less than PORT_CLASS_DEVICE_EXTENSION_SIZE is illegal. Adapter drivers are free to use any part of the device extension after offset PORT_CLASS_DEVICE_EXTENSION_SIZE. They are also free to use bytes in the offset range of 16 to 31 inclusive in a system with 32-bit addressing and bytes in the offset range 32 to 63 in a system with 64-bit addressing. If the extension is regarded as an array of ULONG_PTR, array elements four through seven are available for use by the adapter driver.

The <i>StartDevice</i> parameter points to a function of type PCPFNSTARTDEVICE, which header file <i>portcls.h </i>defines as:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  NTSTATUS
    (*PCPFNSTARTDEVICE)(
      IN PDEVICE_OBJECT  DeviceObject,
      IN PIRP  Irp,
      IN PRESOURCELIST  ResourceList
      );</pre>
</td>
</tr>
</table></span></div>
For more information about <b>PcAddAdapterDevice</b> and the adapter driver's device-startup and <i>AddDevice </i>routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/startup-sequence">Startup Sequence</a>.

The following example code shows how an adapter driver can use the <i>DeviceExtensionSize </i>parameter to append 64 bytes of device-specific extension data to the end of the storage block that PortCls allocates for the device context:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  #define MY_EXTENSION_SIZE  64
  NTSTATUS  ntstatus = PcAddAdapterDevice(DriverObject, PhysicalDeviceObject,
                                          MyStartDevice, MAX_MINIPORTS,
                                          MY_EXTENSION_SIZE + PORT_CLASS_DEVICE_EXTENSION_SIZE);</pre>
</td>
</tr>
</table></span></div>
The <b>PcAddAdapterDevice</b> call above is similar to the example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/startup-sequence">Startup Sequence</a>, except that the last parameter that is passed to <b>PcAddAdapterDevice</b> is nonzero.

The adapter driver can then access the device-specific extension data, as shown in the following code fragment:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  PVOID  pMyExtensionData = (PVOID)((PCHAR)FunctionalDeviceObject->DeviceExtension +
                                              PORT_CLASS_DEVICE_EXTENSION_SIZE);</pre>
</td>
</tr>
</table></span></div>
Variable <i>FunctionalDeviceObject</i> is a pointer to the audio adapter's FDO, and <i>pMyExtensionData</i> is a temporary pointer to the extension data. Avoid confusing the FDO with the PDO, which belongs to the PCI bus driver. The adapter driver must not modify data in the PDO because doing so corrupts memory owned by the PCI bus driver and can cause the system to crash.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>
 

 

