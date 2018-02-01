---
UID: NF:srb.ScsiPortGetBusData
title: ScsiPortGetBusData function
author: windows-driver-content
description: The ScsiPortGetBusData routine returns bus-type-specific configuration information that a miniport driver's HwScsiFindAdapter routine might use to determine whether it supports a particular adapter on a particular I/O bus, and to configure the HBA if it does.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportgetbusdata.htm
old-project: storage
ms.assetid: 43d30c99-9f9e-4516-8c50-e096f760a774
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiPortGetBusData, ScsiPortGetBusData routine [Storage Devices], srb/ScsiPortGetBusData, scsiprt_85566dfe-b1b6-4b6d-9f80-69fbdd82904a.xml, storage.scsiportgetbusdata
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Scsiport.lib
-	Scsiport.dll
apiname:
-	ScsiPortGetBusData
product: Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# ScsiPortGetBusData function


## -description


The <b>ScsiPortGetBusData</b> routine returns bus-type-specific configuration information that a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine might use to determine whether it supports a particular adapter on a particular I/O bus, and to configure the HBA if it does.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
ULONG ScsiPortGetBusData(
  _In_ PVOID DeviceExtension,
  _In_ ULONG BusDataType,
  _In_ ULONG SystemIoBusNumber,
  _In_ ULONG SlotNumber,
  _In_ PVOID Buffer,
  _In_ ULONG Length
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


### -param BusDataType [in]

Contains a value of type <a href="..\ntddk\ne-ntddk-_bus_data_type.md">BUS_DATA_TYPE</a> that specifies the type of bus-specific configuration data to be returned. Currently, this value can be one of the following: <b>Cmos</b>, <b>EisaConfiguration</b>, <b>Pos</b>, or <b>PCIConfiguration</b>. However, additional types of bus configuration will be supported in the future. The upper bound on the types supported is always <b>MaximumBusDataType</b>.


### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus. The miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine obtains this value from the input PORT_CONFIGURATION_INFORMATION <b>SystemIoBusNumber</b> member.


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


<b>ScsiPortGetBusData</b> can be called only from a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine or from <i>HwScsiAdapterControl</i> when the control type is <b>ScsiSetRunningConfig</b>. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

Configuration data returned by <b>ScsiPortGetBusData</b> is valid only until the miniport driver calls <b>ScsiPortGetBusData</b> again. As soon as the caller's <i>HwScsiFindAdapter</i> routine returns control, any returned configuration data becomes invalid.



## -see-also

<a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a>

<a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION (SCSI)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>

<a href="..\wdm\ns-wdm-_pci_slot_number.md">PCI_SLOT_NUMBER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortGetBusData routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

