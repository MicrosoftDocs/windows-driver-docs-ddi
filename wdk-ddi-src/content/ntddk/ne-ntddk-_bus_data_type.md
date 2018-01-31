---
UID: NE:ntddk._BUS_DATA_TYPE
title: "_BUS_DATA_TYPE"
author: windows-driver-content
description: The BUS_DATA_TYPE enumeration indicates the type of bus configuration space.
old-location: kernel\bus_data_type.htm
old-project: kernel
ms.assetid: a2a2e964-b9ae-4367-85de-f0ebe3c7a952
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/MPSAConfiguration, ntddk/PCMCIAConfiguration, PNPISAConfiguration, ntddk/Cmos, ntddk/CbusConfiguration, PBUS_DATA_TYPE, ntddk/VMEConfiguration, ntddk/PNPISAConfiguration, CbusConfiguration, VMEConfiguration, ntddk/MPIConfiguration, ntddk/NuBusConfiguration, PCIConfiguration, MPIConfiguration, MaximumBusDataType, ntddk/Pos, BUS_DATA_TYPE enumeration [Kernel-Mode Driver Architecture], ConfigurationSpaceUndefined, ntddk/PBUS_DATA_TYPE, BUS_DATA_TYPE, ntddk/MaximumBusDataType, PBUS_DATA_TYPE enumeration pointer [Kernel-Mode Driver Architecture], SgiInternalConfiguration, Pos, MPSAConfiguration, EisaConfiguration, ntddk/SgiInternalConfiguration, ntddk/EisaConfiguration, ntddk/ConfigurationSpaceUndefined, sysenum_3f6df31a-39d8-463e-8d44-44e51cd9989d.xml, _BUS_DATA_TYPE, *PBUS_DATA_TYPE, Cmos, ntddk/PCIConfiguration, ntddk/BUS_DATA_TYPE, PCMCIAConfiguration, kernel.bus_data_type, NuBusConfiguration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	BUS_DATA_TYPE
product: Windows
targetos: Windows
req.typenames: BUS_DATA_TYPE, *PBUS_DATA_TYPE
---

# _BUS_DATA_TYPE enumeration


## -description


The <b>BUS_DATA_TYPE</b> enumeration indicates the type of bus configuration space.


## -syntax


````
typedef enum _BUS_DATA_TYPE { 
  ConfigurationSpaceUndefined  = -1,
  Cmos                         = 0,
  EisaConfiguration            = 1,
  Pos                          = 2,
  CbusConfiguration            = 3,
  PCIConfiguration             = 4,
  VMEConfiguration             = 5,
  NuBusConfiguration           = 6,
  PCMCIAConfiguration          = 7,
  MPIConfiguration             = 8,
  MPSAConfiguration            = 9,
  PNPISAConfiguration          = 10,
  SgiInternalConfiguration     = 11,
  MaximumBusDataType           = 12
} BUS_DATA_TYPE, *PBUS_DATA_TYPE;
````


## -enum-fields




#### - ConfigurationSpaceUndefined

Indicates that the type of bus configuration space is undefined.


#### - Cmos

Indicates CMOS data.


#### - EisaConfiguration

Indicates an EISA bus configuration space.


#### - Pos

For internal use only.


#### - CbusConfiguration

Indicates Cbus configuration space.


#### - PCIConfiguration

Indicates PCI configuration space.


#### - VMEConfiguration

Indicates VME configuration space.


#### - NuBusConfiguration

Indicates NuBus configuration space.


#### - PCMCIAConfiguration

Indicates PCMCIA configuration space.


#### - MPIConfiguration

Indicates MPI configuration space.


#### - MPSAConfiguration

Indicates MPSA configuration space.


#### - PNPISAConfiguration

Indicates PNPISA configuration space.


#### - SgiInternalConfiguration

Indicates SGI internal bus configuration space.


#### - MaximumBusDataType

Indicates the upper limit of the bus configuration space types.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546628">HalSetBusData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BUS_DATA_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

