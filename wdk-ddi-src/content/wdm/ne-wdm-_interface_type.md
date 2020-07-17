---
UID: NE:wdm._INTERFACE_TYPE
title: _INTERFACE_TYPE (wdm.h)
description: The INTERFACE_TYPE enumeration indicates the bus type.
old-location: kernel\interface_type.htm
tech.root: kernel
ms.assetid: 4d20f3fd-d06e-420b-af69-9ef34addc611
ms.date: 04/30/2018
keywords: ["_INTERFACE_TYPE enumeration"]
ms.keywords: "*PINTERFACE_TYPE, ACPIBus, CBus, Eisa, INTERFACE_TYPE, INTERFACE_TYPE enumeration [Kernel-Mode Driver Architecture], InterfaceTypeUndefined, Internal, InternalPowerBus, Isa, MPIBus, MPSABus, MaximumInterfaceType, MicroChannel, NuBus, PCIBus, PCMCIABus, PINTERFACE_TYPE, PINTERFACE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], PNPBus, PNPISABus, ProcessorInternal, TurboChannel, VMEBus, Vmcs, _INTERFACE_TYPE, kernel.interface_type, sysenum_a73e08e6-79ef-4a5b-82b1-cfd4bc4269f8.xml, wdm/ACPIBus, wdm/CBus, wdm/Eisa, wdm/INTERFACE_TYPE, wdm/InterfaceTypeUndefined, wdm/Internal, wdm/InternalPowerBus, wdm/Isa, wdm/MPIBus, wdm/MPSABus, wdm/MaximumInterfaceType, wdm/MicroChannel, wdm/NuBus, wdm/PCIBus, wdm/PCMCIABus, wdm/PINTERFACE_TYPE, wdm/PNPBus, wdm/PNPISABus, wdm/ProcessorInternal, wdm/TurboChannel, wdm/VMEBus, wdm/Vmcs"
f1_keywords:
 - "wdm/INTERFACE_TYPE"
 - "INTERFACE_TYPE"
req.header: wdm.h
req.include-header: Wdm.h, Miniport.h, Wudfwdm.h
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
- Wdm.h
api_name:
- INTERFACE_TYPE
product:
- Windows
targetos: Windows
req.typenames: INTERFACE_TYPE, *PINTERFACE_TYPE
---

# _INTERFACE_TYPE enumeration


## -description


The <b>INTERFACE_TYPE</b> enumeration indicates the bus type. 


## -enum-fields




### -field InterfaceTypeUndefined

Indicates that the interface type is undefined. 


### -field Internal

For internal use only. 


### -field Isa

Indicates that the interface is published by the ISA bus driver. 


### -field Eisa

Indicates that the interface is published by the EISA bus driver. 


### -field MicroChannel

Indicates that the interface is published by the MicroChannel bus driver.


### -field TurboChannel

Indicates that the interface is published by the TurboChannel bus driver.


### -field PCIBus

Indicates that the interface is published by the PCI bus driver.


### -field VMEBus

Indicates that the interface is published by the VME bus driver.


### -field NuBus

Indicates that the interface is published by the NuBus driver.


### -field PCMCIABus

Indicates that the interface is published by the PCMCIA bus driver.


### -field CBus

Indicates that the interface is published by the Cbus driver.


### -field MPIBus

Indicates that the interface is published by the MPI bus driver.


### -field MPSABus

Indicates that the interface is published by the MPSA bus driver.


### -field ProcessorInternal

Indicates that the interface is published by the ISA bus driver.


### -field InternalPowerBus

Indicates that the interface is published for an internal power bus. Some devices have power control ports that allow them to share power control with other devices. The Windows architecture represents these devices as slots on a virtual bus called an "internal power bus." 


### -field PNPISABus

Indicates that the interface is published by the PNPISA bus driver.


### -field PNPBus

Indicates that the interface is published by the PNP bus driver.


### -field Vmcs

Reserved for use by the operating system.


### -field ACPIBus

Indicates that the interface is published by the ACPI bus driver. The ACPI bus driver enumerates devices that are described in the ACPI firmware of the hardware platform. These devices might physically reside on buses that are controlled by other bus drivers, but the ACPI bus driver must enumerate these devices because the other bus drivers cannot detect them. This interface type is defined starting with Windows 8.


### -field MaximumInterfaceType

Marks the upper limit of the possible bus types.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportvalidaterange">ScsiPortValidateRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdevicebase">StorPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportvalidaterange">StorPortValidateRange</a>
 

 

