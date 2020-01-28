---
UID: NF:storport.StorPortSetBusDataByOffset
title: StorPortSetBusDataByOffset function (storport.h)
description: The StorPortSetBusDataByOffset routine writes bus-specific configuration information.
old-location: storage\storportsetbusdatabyoffset.htm
tech.root: storage
ms.assetid: ec1db013-b630-421b-8d22-385a2d9b9510
ms.date: 03/29/2018
ms.keywords: StorPortSetBusDataByOffset, StorPortSetBusDataByOffset routine [Storage Devices], storage.storportsetbusdatabyoffset, storport/StorPortSetBusDataByOffset, storprt_ebb2afc1-b190-4674-8ee7-bd61953565ab.xml
f1_keywords:
 - "storport/StorPortSetBusDataByOffset"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortSetBusDataByOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortSetBusDataByOffset function


## -description


The <b>StorPortSetBusDataByOffset</b> routine writes bus-specific configuration information.


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area. 


### -param BusDataType [in]

Contains a value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_bus_data_type">BUS_DATA_TYPE</a> that specifies the type of the bus for which configuration information is to be written. Currently, its value can be <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses will be supported in future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>. 


### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a> routine obtains this value from the input <b>PORT_CONFIGURATION_INFORMATION</b><b>SystemIoBusNumber</b> member. 


### -param SlotNumber [in]

Indicates the logical slot number of the HBA.

When <b>PCIConfiguration</b> is specified as the <i>BusDataType</i>, this parameter must be specified as a PCI_SLOT_NUMBER-type value. 


### -param Buffer [in]

Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>. 

When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the PCI_COMMON_CONFIG information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied. 


### -param Offset [in]

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG. 


### -param Length [in]

Indicates the length, in bytes, of the maximum amount of data to return. 


## -returns



<b>StorPortSetBusDataByOffset</b> returns the number of bytes of configuration data written. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportsetbusdatabyoffset">ScsiPortSetBusDataByOffset</a>
 

 

