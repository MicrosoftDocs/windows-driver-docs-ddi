---
UID: NF:srb.ScsiPortValidateRange
title: ScsiPortValidateRange function (srb.h)
description: The ScsiPortValidateRange routine indicates whether the specified access range values have already been claimed in the registry by another driver.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportvalidaterange.htm
tech.root: storage
ms.assetid: a9ad58c2-16fc-410a-abc7-01c3f2354b88
ms.date: 03/29/2018
ms.keywords: ScsiPortValidateRange, ScsiPortValidateRange routine [Storage Devices], scsiprt_a5bae9f5-7912-4607-890d-ca08fda0c19c.xml, srb/ScsiPortValidateRange, storage.scsiportvalidaterange
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortValidateRange
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortValidateRange function


## -description


The <b>ScsiPortValidateRange</b> routine indicates whether the specified access range values have already been claimed in the registry by another driver.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param HwDeviceExtension [in]

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param BusType [in]

Specifies the value of the <b>AdapterInterfaceType</b> member in the PORT_CONFIGURATION_INFORMATION structure when <i>HwScsiFindAdapter</i> is called.


### -param SystemIoBusNumber [in]

Specifies the value of the <b>SystemIoBusNumber</b> member in the configuration information when <i>HwScsiFindAdapter</i> is called.


### -param IoAddress [in]

Specifies a bus-relative base address for the range of ports or device memory to be validated <i>before</i> the miniport driver's <i>HwScsiFindAdapter</i> routine attempts to map the access range for the adapter at that address.


### -param NumberOfBytes [in]

Specifies the size in bytes or number of elements in the range.


### -param InIoSpace [in]

Indicates when TRUE that the range is in I/O space, rather than in memory. When <b>FALSE</b>, the range is in memory space. 


## -returns



<b>ScsiPortValidateRange</b> returns <b>TRUE</b> if the HwScsiFindAdapter routine can safely map and use the mapped range to access the adapter. <b>ScsiPortValidateRange</b> returns <b>FALSE</b> if the specified access range values have already been claimed in the registry by another driver.




## -remarks



<b>ScsiPortValidateRange </b>can be called only from a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

If the operating system-specific port driver initializes any <b>AccessRanges</b> element of the PORT_CONFIGURATION_INFORMATION structure before it calls the miniport driver's <i>HwScsiFindAdapter</i> routine, the miniport driver must pass the supplied values to <b>ScsiPortGetDeviceBase</b> and use the mapped logical addresses for the range to determine whether an HBA is one that it supports.

The port driver either fills an ACCESS_RANGE-type element with a complete description of a bus-relative address range for an adapter, or the port driver zeros all members of the element.

For input <b>AccessRanges</b> elements set with default zeros, the <i>HwScsiFindAdapter</i> routine can attempt to locate an adapter it supports on the given I/O bus. In these circumstances, a miniport driver usually has a set of driver-determined default addresses for its type(s) of HBA. However, a previously loaded driver might already be using an initialized adapter at one of this miniport driver's default address ranges, particularly in x86-only systems in which some devices are initialized in x86 real mode. To prevent such a device from being inadvertently reprogrammed, each miniport driver's <i>HwScsiFindAdapter</i> routine should call <b>ScsiPortValidateRange</b> before it maps any driver-supplied addresses with <b>ScsiPortGetDeviceBase</b> and then uses the mapped logical addresses to interrogate adapters on an I/O bus.

If <b>ScsiPortValidateRange</b> returns <b>FALSE</b>, <i>HwScsiFindAdapter</i> must not attempt to map the input range addresses because another driver has already claimed the range in the registry.

If <b>ScsiPortValidateRange</b> returns <b>TRUE</b>, <i>HwScsiFindAdapter</i> can safely do the following:

<ol>
<li>
Map the bus-relative range addresses to system-space logical range addresses with <b>ScsiPortGetDeviceBase</b>.

</li>
<li>
Use the mapped logical addresses with the <b>ScsiPortRead/Write</b><i>Xxx</i> to determine whether the adapter actually is an HBA that the driver supports.

</li>
</ol>
If a miniport driver uses a range successfully passed to <b>ScsiPortValidateRange</b> for an HBA it supports, that driver must invert the <i>InIoSpace</i> value when it sets the <b>RangeInMemory</b> member of an <b>AccessRanges</b> element in the PORT_CONFIGURATION_INFORMATION.

<b>ScsiPortValidateRange</b> uses <b>SCSI_PHYSICAL_ADDRESS</b> to represent bus-relative addresses.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef PHYSICAL_ADDRESS SCSI_PHYSICAL_ADDRESS, *PSCSI_PHYSICAL_ADDRESS;
</pre>
</td>
</tr>
</table></span></div>
The <b>SCSI_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that SCSI miniport drivers use to represent either a physical addresses or a bus-relative address. 

<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550117">ACCESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563900">PORT_CONFIGURATION_INFORMATION (SCSI)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>
 

 

