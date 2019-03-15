---
UID: NS:strmini._PORT_CONFIGURATION_INFORMATION
title: _PORT_CONFIGURATION_INFORMATION (strmini.h)
description: PORT_CONFIGURATION_INFORMATION describes the hardware settings of a streaming minidriver's device. The class driver fills in most members with information provided by the operating system.
old-location: stream\port_configuration_information.htm
tech.root: stream
ms.assetid: fa990867-4e2f-4940-b6fc-310ec7fc2b68
ms.date: 04/23/2018
ms.keywords: "*PPORT_CONFIGURATION_INFORMATION, PORT_CONFIGURATION_INFORMATION, PORT_CONFIGURATION_INFORMATION structure [Streaming Media Devices], PPORT_CONFIGURATION_INFORMATION, PPORT_CONFIGURATION_INFORMATION structure pointer [Streaming Media Devices], _PORT_CONFIGURATION_INFORMATION, _PORT_CONFIGURATION_INFORMATION structure [Streaming Media Devices], strclass-struct_5cfaddef-5c60-406e-b938-697f36b6c8e1.xml, stream.port_configuration_information, strmini/PORT_CONFIGURATION_INFORMATION, strmini/PPORT_CONFIGURATION_INFORMATION"
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
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
- strmini.h
api_name:
- PORT_CONFIGURATION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PORT_CONFIGURATION_INFORMATION, *PPORT_CONFIGURATION_INFORMATION
---

# _PORT_CONFIGURATION_INFORMATION structure


## -description


PORT_CONFIGURATION_INFORMATION describes the hardware settings of a streaming minidriver's device. The class driver fills in most members with information provided by the operating system.


## -struct-fields




### -field SizeOfThisPacket

The size of this structure, in bytes. The class driver fills in this member.


### -field HwDeviceExtension

Pointer to the minidriver's device extension. The minidriver may use this buffer to record private information global to the minidriver. The minidriver sets the size of this buffer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559706">HW_TIME_CONTEXT</a> structures it passes to the minidriver.


### -field ClassDeviceObject

Points to the class-driver-provided functional device object (FDO) for the driver's device.


### -field PhysicalDeviceObject

Points to the device object for the driver at the top of the driver stack when the class driver attaches to the driver stack. Drivers use this member when calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a> to communicate with the driver stack. The <b>RealPhysicalDeviceObject</b> member points to the actual PDO for the driver's device.


### -field SystemIoBusNumber

The class driver fills in this member with the system bus ID number of the device. Bus 0 is the primary system bus. 


### -field AdapterInterfaceType

Specifies the type of system bus the device is connected to. Possible values include <b>Isa</b>, <b>Eisa</b>, <b>MicroChannel</b>, <b>PCIBus</b>, and <b>PCMCIABus</b>. 


### -field BusInterruptLevel

The class driver fills in this member with the IRQL for interrupts on this bus.


### -field BusInterruptVector

The class driver fills in this member with the interrupt vector used by the device.


### -field InterruptMode

The class driver fills in this member with the interrupt mode, either Latched or LevelSensitive.


### -field DmaChannel

If the device connects to the ISA bus, the class driver fills in this member with the DMA channel of the device.


### -field NumberOfAccessRanges

The number of entries in the <b>AccessRanges</b> array.


### -field AccessRanges

The number of entries in the <b>AccessRanges</b> array.


### -field StreamDescriptorSize

The minidriver fills in this member with the size of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff559686">HW_STREAM_DESCRIPTOR</a> structure.


### -field Irp

Pointer to the PnP device start IRP that triggered this SRB_INITIALIZE_DEVICE request.


### -field InterruptObject

If the device uses interrupts, the class driver fills in this member with a pointer to the associated Interrupt object. 


### -field DmaAdapterObject

If the device uses DMA, the class driver fills in this member with a pointer to the associated DmaAdapter object.


### -field RealPhysicalDeviceObject

Pointer to the PDO for the driver's device.


### -field Reserved

Reserved for system use. Do not use.


## -remarks



Most of the members of PORT_CONFIGURATION_INFORMATION provide information to the minidriver about its use of hardware resources, such as its interrupt vector and the IRQL for its interrupts.



