---
UID: NF:srb.ScsiPortGetBusData
title: ScsiPortGetBusData function (srb.h)
description: The ScsiPortGetBusData routine returns bus-type-specific configuration information that a miniport driver's HwScsiFindAdapter routine might use to determine whether it supports a particular adapter on a particular I/O bus, and to configure the HBA if it does.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportgetbusdata.htm
tech.root: storage
ms.assetid: 43d30c99-9f9e-4516-8c50-e096f760a774
ms.date: 03/29/2018
ms.keywords: ScsiPortGetBusData, ScsiPortGetBusData routine [Storage Devices], scsiprt_85566dfe-b1b6-4b6d-9f80-69fbdd82904a.xml, srb/ScsiPortGetBusData, storage.scsiportgetbusdata
f1_keywords:
 - "srb/ScsiPortGetBusData"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortGetBusData
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortGetBusData function


## -description


The <b>ScsiPortGetBusData</b> routine returns bus-type-specific configuration information that a miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine might use to determine whether it supports a particular adapter on a particular I/O bus, and to configure the HBA if it does.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


### -param BusDataType [in]

Contains a value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bus_data_type">BUS_DATA_TYPE</a> that specifies the type of bus-specific configuration data to be returned. Currently, this value can be one of the following: <b>Cmos</b>, <b>EisaConfiguration</b>, <b>Pos</b>, or <b>PCIConfiguration</b>. However, additional types of bus configuration will be supported in the future. The upper bound on the types supported is always <b>MaximumBusDataType</b>.


### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus. The miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine obtains this value from the input PORT_CONFIGURATION_INFORMATION <b>SystemIoBusNumber</b> member.


### -param SlotNumber [in]

Specifies the logical slot number or location of the device.

If <b>PCIConfiguration</b> is specified as the <i>BusDataType</i>, this parameter must be specified as a PCI_SLOT_NUMBER-type value.


### -param Buffer [in]

Pointer to a buffer or area to which the configuration data is returned or, if the given <i>Length</i> is zero, points to a location to which the operating system-specific port driver returns a pointer to a buffer that it allocates.


### -param Length [in]

Specifies the maximum number of bytes to return at <i>Buffer</i>, or zero if the caller requires the operating system-specific port driver to allocate a buffer to contain the data.


## -returns



<b>ScsiPortGetBusData</b> returns the number of bytes of configuration information it stored in the buffer. When the input BusDataType is PCIConfiguration, ScsiPortGetBusData can return either of the following values to indicate an error.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>0 (zero)</b></dt>
</dl>
</td>
<td width="60%">
The PCI bus does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>2</b></dt>
</dl>
</td>
<td width="60%">
The PCI bus exists, but there is no device at the given PCI <i>SlotNumber</i>. The <i>Buffer</i> contains the value PCI_INVALID_VENDOR_ID at the PCI_COMMON_CONFIG <b>VendorId</b> member.

</td>
</tr>
</table>
 




## -remarks



<b>ScsiPortGetBusData</b> can be called only from a miniport driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> routine or from <i>HwScsiAdapterControl</i> when the control type is <b>ScsiSetRunningConfig</b>. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

Configuration data returned by <b>ScsiPortGetBusData</b> is valid only until the miniport driver calls <b>ScsiPortGetBusData</b> again. As soon as the caller's <i>HwScsiFindAdapter</i> routine returns control, any returned configuration data becomes invalid.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_slot_number">PCI_SLOT_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_port_configuration_information">PORT_CONFIGURATION_INFORMATION (SCSI)</a>
 

 

