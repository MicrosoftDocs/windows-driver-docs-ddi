---
UID: NF:srb.ScsiPortSetBusDataByOffset
title: ScsiPortSetBusDataByOffset function
author: windows-driver-content
description: The ScsiPortSetBusDataByOffset routine sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.
old-location: storage\scsiportsetbusdatabyoffset.htm
old-project: storage
ms.assetid: 64f46049-fbf0-4d9b-b5fe-9877a964755f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ScsiPortSetBusDataByOffset, ScsiPortSetBusDataByOffset routine [Storage Devices], scsiprt_83fdaa63-8e40-41e6-8f60-b9cc98c6eade.xml, srb/ScsiPortSetBusDataByOffset, storage.scsiportsetbusdatabyoffset
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
-	ScsiPortSetBusDataByOffset
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---

# ScsiPortSetBusDataByOffset function


## -description


The <b>ScsiPortSetBusDataByOffset</b> routine sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
ULONG ScsiPortSetBusDataByOffset(
  _In_ PVOID DeviceExtension,
  _In_ ULONG BusDataType,
  _In_ ULONG SystemIoBusNumber,
  _In_ ULONG SlotNumber,
  _In_ PVOID Buffer,
  _In_ ULONG Offset,
  _In_ ULONG Length
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's device extension. 


### -param BusDataType [in]

Contains a value of type <a href="..\ntddk\ne-ntddk-_bus_data_type.md">BUS_DATA_TYPE</a> that specifies the type of bus data to be set. Currently, its value can be <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses will be supported in future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>. 


### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The miniport driver's <a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a> routine obtains this value from the input PORT_CONFIGURATION_INFORMATION <b>SystemIoBusNumber</b> member. 


### -param SlotNumber [in]

Specifies the logical slot number of the HBA.

When <b>PCIConfiguration</b> is specified as the <i>BusDataType</i>, this parameter must be specified as a PCI_SLOT_NUMBER-type value. 


### -param Buffer [in]

Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>. 

When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the PCI_COMMON_CONFIG information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied. 


### -param Offset [in]

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG. 


### -param Length [in]

Specifies the number of bytes in the storage area at <i>Buffer</i>. 


## -returns



<b>ScsiPortSetBusDataByOffset</b> returns the number of bytes of data successfully set for the given <i>SlotNumber</i>. If the given <i>BusDataType</i> is not valid for the current platform or if the supplied information is invalid, <b>ScsiPortSetBusDataByOffset</b> returns zero. 




## -remarks



Miniport drivers of HBAs on a PCI bus seldom call <b>ScsiPortSetBusDataByOffset</b> unless unusual circumstances or the nature of a particular driver's HBA requires such a call. For example, a miniport driver might call <b>ScsiPortSetBusDataByOffset</b> to clear a bit in the PCI status register if its HBA signals a target abort during initialization or to set device-specific configuration data for the HBA.

<b>ScsiPortSetBusDataByOffset</b> can be called only from the miniport driver's <i>HwScsiFindAdapter</i> routine or from HwScsiAdapterControl when the control type is <b>ScsiSetRunningConfig</b>. 




## -see-also

<a href="..\wdm\ns-wdm-_pci_slot_number.md">PCI_SLOT_NUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>



<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION (SCSI)</a>



<a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a>



<a href="..\srb\nc-srb-phw_find_adapter.md">HwScsiFindAdapter</a>



<a href="..\srb\nf-srb-scsiportgetbusdata.md">ScsiPortGetBusData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortSetBusDataByOffset routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

