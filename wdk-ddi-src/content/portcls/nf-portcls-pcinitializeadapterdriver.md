---
UID: NF:portcls.PcInitializeAdapterDriver
title: PcInitializeAdapterDriver function (portcls.h)
description: The PcInitializeAdapterDriver function binds an adapter driver to the PortCls system driver.
old-location: audio\pcinitializeadapterdriver.htm
tech.root: audio
ms.assetid: c9d019da-a05b-4c60-99e9-06b8537fa78e
ms.date: 05/08/2018
keywords: ["PcInitializeAdapterDriver function"]
ms.keywords: PcInitializeAdapterDriver, PcInitializeAdapterDriver function [Audio Devices], audio.pcinitializeadapterdriver, audpc-routines_57c7e54d-ab27-4752-b13b-9d7de107322c.xml, portcls/PcInitializeAdapterDriver
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcInitializeAdapterDriver function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PcInitializeAdapterDriver
 - portcls/PcInitializeAdapterDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcInitializeAdapterDriver
---

# PcInitializeAdapterDriver function


## -description

The <b>PcInitializeAdapterDriver</b> function binds an adapter driver to the PortCls system driver. IRP handlers and handlers for device addition and removal are installed in the driver object. Adapter drivers that need to bind to more than one class driver should not call this function.

## -parameters

### -param DriverObject 

[in]
Pointer to the driver object, which is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>. This pointer is passed as a parameter to the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function.

### -param RegistryPathName 

[in]
Specifies the registry path name that is to be passed as a parameter to the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function.

### -param AddDevice 

[in]
Pointer to the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> function. This is a pointer of type PDRIVER_ADD_DEVICE, which is defined in ntddk.h to be:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  NTSTATUS
    (*PDRIVER_ADD_DEVICE)(
      IN struct _DRIVER_OBJECT  *DriverObject,
      IN struct _DEVICE_OBJECT  *PhysicalDeviceObject
        );</pre>
</td>
</tr>
</table></span></div>

## -returns

<b>PcInitializeAdapterDriver</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> handler supplied in the call to this function should call <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/audio-pcaddadapterdevice">PcAddAdapterDevice</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/startup-sequence">Startup Sequence</a>.

The <b>PcInitializeAdapterDriver</b> function loads pointers to handlers for the following IRPs into the driver object:

<ul>
<li>
IRP_MJ_CLOSE

</li>
<li>
IRP_MJ_CREATE

</li>
<li>
IRP_MJ_DEVICE_CONTROL

</li>
<li>
IRP_MJ_FLUSH_BUFFERS

</li>
<li>
IRP_MJ_PNP

</li>
<li>
IRP_MJ_POWER

</li>
<li>
IRP_MJ_QUERY_SECURITY

</li>
<li>
IRP_MJ_READ

</li>
<li>
IRP_MJ_SET_SECURITY

</li>
<li>
IRP_MJ_SYSTEM_CONTROL

</li>
<li>
IRP_MJ_WRITE

</li>
</ul>
PortCls uses its own internal handlers for the CREATE, PNP, POWER, and SYSTEM_CONTROL IRPs above. It uses the default KS handlers for the other seven IRPs.

An adapter driver that overwrites one or more of the pointers above with a pointer to its own IRP handler can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcdispatchirp">PcDispatchIrp</a> from within its handler routine in order to forward the IRP to PortCls. For a code example, see the SB16 sample audio driver in the Microsoft Windows Driver Kit (WDK).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/audio-pcaddadapterdevice">PcAddAdapterDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcdispatchirp">PcDispatchIrp</a>

