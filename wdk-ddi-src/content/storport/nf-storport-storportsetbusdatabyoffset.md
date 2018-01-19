---
UID: NF:storport.StorPortSetBusDataByOffset
title: StorPortSetBusDataByOffset function
author: windows-driver-content
description: The StorPortSetBusDataByOffset routine writes bus-specific configuration information.
old-location: storage\storportsetbusdatabyoffset.htm
old-project: storage
ms.assetid: ec1db013-b630-421b-8d22-385a2d9b9510
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortSetBusDataByOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortSetBusDataByOffset
req.alt-loc: Storport.lib,Storport.dll
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
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortSetBusDataByOffset function



## -description
The <b>StorPortSetBusDataByOffset</b> routine writes bus-specific configuration information.



## -syntax

````
STORPORT_API ULONG StorPortSetBusDataByOffset(
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

Pointer to the miniport driver's per-HBA storage area. 


### -param BusDataType [in]

Contains a value of type <a href="..\ntddk\ne-ntddk-_bus_data_type.md">BUS_DATA_TYPE</a> that specifies the type of the bus for which configuration information is to be written. Currently, its value can be <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses will be supported in future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>. 


### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus on which the HBA is connected. The miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains this value from the input <b>PORT_CONFIGURATION_INFORMATION</b><b>SystemIoBusNumber</b> member. 


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\srb\nf-srb-scsiportsetbusdatabyoffset.md">ScsiPortSetBusDataByOffset</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortSetBusDataByOffset routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

