---
UID: NE:wdm._INTERFACE_TYPE
title: "_INTERFACE_TYPE"
author: windows-driver-content
description: The INTERFACE_TYPE enumeration indicates the bus type.
old-location: kernel\interface_type.htm
old-project: kernel
ms.assetid: 4d20f3fd-d06e-420b-af69-9ef34addc611
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PNPISABus, InternalPowerBus, kernel.interface_type, PCIBus, sysenum_a73e08e6-79ef-4a5b-82b1-cfd4bc4269f8.xml, wdm/ProcessorInternal, _INTERFACE_TYPE, wdm/MaximumInterfaceType, InterfaceTypeUndefined, VMEBus, NuBus, Internal, *PINTERFACE_TYPE, Vmcs, CBus, wdm/TurboChannel, wdm/MicroChannel, wdm/VMEBus, wdm/InterfaceTypeUndefined, wdm/PCIBus, MPSABus, wdm/Internal, ACPIBus, wdm/Eisa, TurboChannel, PNPBus, INTERFACE_TYPE enumeration [Kernel-Mode Driver Architecture], wdm/PCMCIABus, wdm/NuBus, MPIBus, wdm/PNPISABus, PINTERFACE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], MaximumInterfaceType, PINTERFACE_TYPE, MicroChannel, wdm/Vmcs, wdm/CBus, wdm/ACPIBus, wdm/PINTERFACE_TYPE, wdm/PNPBus, wdm/MPIBus, Eisa, PCMCIABus, wdm/MPSABus, wdm/Isa, Isa, wdm/InternalPowerBus, ProcessorInternal, INTERFACE_TYPE, wdm/INTERFACE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	INTERFACE_TYPE
product: Windows
targetos: Windows
req.typenames: INTERFACE_TYPE, *PINTERFACE_TYPE
req.product: Windows 10 or later.
---

# _INTERFACE_TYPE enumeration


## -description


The <b>INTERFACE_TYPE</b> enumeration indicates the bus type. 


## -syntax


````
typedef enum _INTERFACE_TYPE { 
  InterfaceTypeUndefined  = -1,
  Internal,
  Isa,
  Eisa,
  MicroChannel,
  TurboChannel,
  PCIBus,
  VMEBus,
  NuBus,
  PCMCIABus,
  CBus,
  MPIBus,
  MPSABus,
  ProcessorInternal,
  InternalPowerBus,
  PNPISABus,
  PNPBus,
  Vmcs,
  ACPIBus,
  MaximumInterfaceType
} INTERFACE_TYPE, *PINTERFACE_TYPE;
````


## -enum-fields




#### - InterfaceTypeUndefined

Indicates that the interface type is undefined. 


#### - Internal

For internal use only. 


#### - Isa

Indicates that the interface is published by the ISA bus driver. 


#### - Eisa

Indicates that the interface is published by the EISA bus driver. 


#### - MicroChannel

Indicates that the interface is published by the MicroChannel bus driver.


#### - TurboChannel

Indicates that the interface is published by the TurboChannel bus driver.


#### - PCIBus

Indicates that the interface is published by the PCI bus driver.


#### - VMEBus

Indicates that the interface is published by the VME bus driver.


#### - NuBus

Indicates that the interface is published by the NuBus driver.


#### - PCMCIABus

Indicates that the interface is published by the PCMCIA bus driver.


#### - CBus

Indicates that the interface is published by the Cbus driver.


#### - MPIBus

Indicates that the interface is published by the MPI bus driver.


#### - MPSABus

Indicates that the interface is published by the MPSA bus driver.


#### - ProcessorInternal

Indicates that the interface is published by the ISA bus driver.


#### - InternalPowerBus

Indicates that the interface is published for an internal power bus. Some devices have power control ports that allow them to share power control with other devices. The Windows architecture represents these devices as slots on a virtual bus called an "internal power bus." 


#### - PNPISABus

Indicates that the interface is published by the PNPISA bus driver.


#### - PNPBus

Indicates that the interface is published by the PNP bus driver.


#### - Vmcs

Reserved for use by the operating system.


#### - ACPIBus

Indicates that the interface is published by the ACPI bus driver. The ACPI bus driver enumerates devices that are described in the ACPI firmware of the hardware platform. These devices might physically reside on buses that are controlled by other bus drivers, but the ACPI bus driver must enumerate these devices because the other bus drivers cannot detect them. This interface type is defined starting with Windows 8.


#### - MaximumInterfaceType

Marks the upper limit of the possible bus types.


## -see-also

<a href="..\storport\nf-storport-storportvalidaterange.md">StorPortValidateRange</a>

<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>

<a href="..\storport\nf-storport-storportgetdevicebase.md">StorPortGetDeviceBase</a>

<a href="..\srb\nf-srb-scsiportvalidaterange.md">ScsiPortValidateRange</a>

<a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20INTERFACE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

