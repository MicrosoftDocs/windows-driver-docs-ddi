---
UID: NE:ntddk._BUS_DATA_TYPE
title: _BUS_DATA_TYPE (ntddk.h)
description: The BUS_DATA_TYPE enumeration indicates the type of bus configuration space.
old-location: kernel\bus_data_type.htm
tech.root: kernel
ms.assetid: a2a2e964-b9ae-4367-85de-f0ebe3c7a952
ms.date: 04/30/2018
keywords: ["_BUS_DATA_TYPE enumeration"]
ms.keywords: "*PBUS_DATA_TYPE, BUS_DATA_TYPE, BUS_DATA_TYPE enumeration [Kernel-Mode Driver Architecture], CbusConfiguration, Cmos, ConfigurationSpaceUndefined, EisaConfiguration, MPIConfiguration, MPSAConfiguration, MaximumBusDataType, NuBusConfiguration, PBUS_DATA_TYPE, PBUS_DATA_TYPE enumeration pointer [Kernel-Mode Driver Architecture], PCIConfiguration, PCMCIAConfiguration, PNPISAConfiguration, Pos, SgiInternalConfiguration, VMEConfiguration, _BUS_DATA_TYPE, kernel.bus_data_type, ntddk/BUS_DATA_TYPE, ntddk/CbusConfiguration, ntddk/Cmos, ntddk/ConfigurationSpaceUndefined, ntddk/EisaConfiguration, ntddk/MPIConfiguration, ntddk/MPSAConfiguration, ntddk/MaximumBusDataType, ntddk/NuBusConfiguration, ntddk/PBUS_DATA_TYPE, ntddk/PCIConfiguration, ntddk/PCMCIAConfiguration, ntddk/PNPISAConfiguration, ntddk/Pos, ntddk/SgiInternalConfiguration, ntddk/VMEConfiguration, sysenum_3f6df31a-39d8-463e-8d44-44e51cd9989d.xml"
f1_keywords:
 - "ntddk/BUS_DATA_TYPE"
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- BUS_DATA_TYPE
product:
- Windows
targetos: Windows
req.typenames: BUS_DATA_TYPE, *PBUS_DATA_TYPE
---

# _BUS_DATA_TYPE enumeration


## -description


The <b>BUS_DATA_TYPE</b> enumeration indicates the type of bus configuration space.


## -enum-fields




### -field ConfigurationSpaceUndefined

Indicates that the type of bus configuration space is undefined.


### -field Cmos

Indicates CMOS data.


### -field EisaConfiguration

Indicates an EISA bus configuration space.


### -field Pos

For internal use only.


### -field CbusConfiguration

Indicates Cbus configuration space.


### -field PCIConfiguration

Indicates PCI configuration space.


### -field VMEConfiguration

Indicates VME configuration space.


### -field NuBusConfiguration

Indicates NuBus configuration space.


### -field PCMCIAConfiguration

Indicates PCMCIA configuration space.


### -field MPIConfiguration

Indicates MPI configuration space.


### -field MPSAConfiguration

Indicates MPSA configuration space.


### -field PNPISAConfiguration

Indicates PNPISA configuration space.


### -field SgiInternalConfiguration

Indicates SGI internal bus configuration space.


### -field MaximumBusDataType

Indicates the upper limit of the bus configuration space types.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusData</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusDataByOffset</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalSetBusData</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalSetBusDataByOffset</a>
 

 

