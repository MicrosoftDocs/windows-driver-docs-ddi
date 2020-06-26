---
UID: NC:wmilib.WMI_QUERY_REGINFO_CALLBACK
title: WMI_QUERY_REGINFO_CALLBACK (wmilib.h)
description: The DpWmiQueryReginfo routine provides information about the data blocks and event blocks to be registered by a driver. This routine is required.
old-location: kernel\dpwmiqueryreginfo.htm
tech.root: kernel
ms.assetid: 6e450788-445f-4d0a-b99b-913100a54259
ms.date: 04/30/2018
keywords: ["WMI_QUERY_REGINFO_CALLBACK callback function"]
ms.keywords: DpWmiQueryReginfo, DpWmiQueryReginfo callback function [Kernel-Mode Driver Architecture], WMI_QUERY_REGINFO_CALLBACK, WMI_QUERY_REGINFO_CALLBACK callback, k903_61d9ad7d-1bdf-49d5-8a12-5bf0d6912ccc.xml, kernel.dpwmiqueryreginfo, wmilib/DpWmiQueryReginfo
f1_keywords:
 - "wmilib/DpWmiQueryReginfo"
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wmilib.h
api_name:
- DpWmiQueryReginfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# WMI_QUERY_REGINFO_CALLBACK callback function


## -description


The <i>DpWmiQueryReginfo</i> routine provides information about the data blocks and event blocks to be registered by a driver. This routine is required.


## -parameters




### -param DeviceObject [in]

A pointer to the driver's WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.


### -param RegFlags [out]

This parameter indicates common characteristics of all blocks being registered. Any flag set in <i>RegFlags</i> is applied to all blocks. A driver can supplement <i>RegFlags</i> for a given block by setting <b>Flags</b> in the block's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmiguidreginfo">WMIGUIDREGINFO</a> structure. For example, a driver might clear WMIREG_FLAG_EXPENSIVE in <i>RegFlags</i>, but set it in <b>Flags</b> to register a given block as expensive to collect.

The driver sets one of the following flags in <i>RegFlags</i>:





#### WMIREG_FLAG_INSTANCE_BASENAME

Requests WMI to generate static instance names from a base name provided by the driver at the <i>InstanceName</i>. WMI generates instance names by appending a counter to the base name.



#### WMIREG_FLAG_INSTANCE_PDO

Requests WMI to generate static instance names from the device instance ID for the PDO. If the driver sets this flag, it must also set <i>Pdo</i> to the PDO passed to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine. WMI generates instance names from the device instance path of the PDO. Using the device instance path as a base for static instance names is efficient because such names are guaranteed to be unique. WMI automatically supplies a "friendly" name for the instance as an item in a data block that can be queried by data consumers.

A driver might also set one or more of the following flags in <i>RegFlags</i>, but more typically would set them in <b>Flags</b> of a block's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmiguidreginfo">WMIGUIDREGINFO</a> structure:





#### WMIREG_FLAG_EVENT_ONLY_GUID

The blocks can be enabled or disabled as events only, and cannot be queried or set. If this flag is clear, the blocks can also be queried or set. 



#### WMIREG_FLAG_EXPENSIVE

Requests WMI to send an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-enable-collection">IRP_MN_ENABLE_COLLECTION</a> request the first time a data consumer opens a data block and an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-disable-collection">IRP_MN_DISABLE_COLLECTION</a> request when the last data consumer closes the data block. This is recommended if collecting such data affects performance, because a driver need not collect the data until a data consumer explicitly requests it by opening the block. 



#### WMIREG_FLAG_REMOVE_GUID

Requests WMI to remove support for the blocks. This flag is valid only in response to a request to update registration information (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath</b> set to WMIUPDATE).


### -param InstanceName [out]

A pointer to a single counted Unicode string that serves as the base name for all instances of all blocks to be registered by the driver. WMI frees the string with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>. If WMIREG_FLAG_INSTANCE_BASENAME is clear, <i>InstanceName</i> is ignored.


### -param RegistryPath [out]

A pointer to a pointer to a counted Unicode string that specifies the registry path passed to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. 


### -param MofResourceName [out]

A pointer to a single counted Unicode string that indicates the name of the MOF resource attached to the driver's binary image file. Typically this string would be a static defined by the driver. WMI makes a copy of this string after the driver returns from this routine. This string can be dynamically allocated by the driver. In the case of an allocated string, the driver is responsible for freeing the string which should be done after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a> returns. If the driver does not have a MOF resource attached, it can leave <i>MofResourceName</i> unchanged. 


### -param Pdo [out]

A pointer to the physical device object (PDO) passed to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine. If WMIREG_FLAG_INSTANCE_PDO is set, WMI uses the device instance path of this PDO as a base from which to generate static instance names. If WMIREG_FLAG_INSTANCE_PDO is clear, WMI ignores <i>Pdo</i>.


## -returns



<i>DpWmiQueryReginfo</i> always returns STATUS_SUCCESS.




## -remarks



WMI calls a driver's <i>DpWmiQueryReginfo</i> routine after the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a> in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> request. The driver must place the address of its <i>DpWmiQueryReginfo</i> routine in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a> structure that it passes to <b>WmiSystemControl</b>.

WMI sends the IRP after a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiregistrationcontrol">IoWMIRegistrationControl</a> with WMIREG_ACTION_REGISTER, WMIREG_ACTION_REREGISTER, or WMIREG_ACTION_UPDATE. WMI transparently handles the differences between <b>IRP_MN_REGINFO</b> and <b>IRP_MN_REGINFO_EX</b> on behalf of the driver.

WMI does not send an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> request after a driver calls <b>IoWMIRegistrationControl</b> with WMIREG_ACTION_DEREGISTER, because WMI requires no further information from the driver. A driver typically deregisters its blocks in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> request. 

The driver provides new or updated registration information about individual blocks, or indicates blocks to remove, in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a> structure it passes to <b>WmiSystemControl</b>. After the initial call, which establishes the driver's registry path and MOF resource name, a driver's <i>DpWmiQueryReginfo</i> routine can change flags common to all of a driver's blocks, provide a different base name string used to generate instance names, or change the basis for instance names from a string to the device instance path of the PDO. 

The driver must not return STATUS_PENDING or block the request. The driver must not complete the request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmicompleterequest">WmiCompleteRequest</a> from its <i>DpWmiQueryReginfo</i> routine or by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a> after <b>WmiSystemControl</b> returns.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/calling-wmisystemcontrol-to-handle-wmi-irps">Calling WmiSystemControl to Handle WMI IRPs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiregistrationcontrol">IoWMIRegistrationControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmiguidreginfo">WMIGUIDREGINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/ns-wmilib-_wmilib_context">WMILIB_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmisystemcontrol">WmiSystemControl</a>
 

 

