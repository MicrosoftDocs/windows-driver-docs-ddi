---
UID: NE:ntddk._WHEA_RAW_DATA_FORMAT
title: "_WHEA_RAW_DATA_FORMAT"
author: windows-driver-content
description: The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet.
old-location: whea\whea_raw_data_format.htm
old-project: whea
ms.assetid: 809f2d72-e769-48c1-9ecf-6fa9020f6cdb
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_RAW_DATA_FORMAT, PWHEA_RAW_DATA_FORMAT, PWHEA_RAW_DATA_FORMAT enumeration pointer [WHEA Drivers and Applications], WHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT enumeration [WHEA Drivers and Applications], WheaRawDataFormatAMD64MCA, WheaRawDataFormatGeneric, WheaRawDataFormatIA32MCA, WheaRawDataFormatIPFSalRecord, WheaRawDataFormatIntel64MCA, WheaRawDataFormatMax, WheaRawDataFormatMemory, WheaRawDataFormatNMIPort, WheaRawDataFormatPCIExpress, WheaRawDataFormatPCIXBus, WheaRawDataFormatPCIXDevice, _WHEA_RAW_DATA_FORMAT, ntddk/PWHEA_RAW_DATA_FORMAT, ntddk/WHEA_RAW_DATA_FORMAT, ntddk/WheaRawDataFormatAMD64MCA, ntddk/WheaRawDataFormatGeneric, ntddk/WheaRawDataFormatIA32MCA, ntddk/WheaRawDataFormatIPFSalRecord, ntddk/WheaRawDataFormatIntel64MCA, ntddk/WheaRawDataFormatMax, ntddk/WheaRawDataFormatMemory, ntddk/WheaRawDataFormatNMIPort, ntddk/WheaRawDataFormatPCIExpress, ntddk/WheaRawDataFormatPCIXBus, ntddk/WheaRawDataFormatPCIXDevice, whea.whea_raw_data_format, whearef_9ecb0580-4372-40f3-93da-4f866ee6211f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_RAW_DATA_FORMAT
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# _WHEA_RAW_DATA_FORMAT enumeration


## -description


The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet.


## -enum-fields




### -field WheaRawDataFormatIPFSalRecord

The raw data in the hardware error packet contains an Itanium processor family system abstraction layer (SAL) error record. For more information about the format of a SAL error record, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.


### -field WheaRawDataFormatIA32MCA

The raw data in the hardware error packet contains an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.


### -field WheaRawDataFormatIntel64MCA

The raw data in the hardware error packet contains an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.


### -field WheaRawDataFormatAMD64MCA

The raw data in the hardware error packet contains an MCA_EXCEPTION structure. For more information about the MCA_EXCEPTION structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>.


### -field WheaRawDataFormatMemory

The raw data in the hardware error packet contains memory error data. The format of this error data is memory architecture-dependent.


### -field WheaRawDataFormatPCIExpress

The raw data in the hardware error packet contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a> structure.


### -field WheaRawDataFormatNMIPort

The raw data in the hardware error packet contains the data that was read from the nonmaskable interrupt (NMI) I/O ports by the NMI low-level hardware error handler (LLHEH).


### -field WheaRawDataFormatPCIXBus

The raw data in the hardware error packet contains PCI/PCI-X bus error data. The format of this error data is specific to the implementation.


### -field WheaRawDataFormatPCIXDevice

The raw data in the hardware error packet contains a PCI/PCI-X device error data. The format of this error data is specific to the implementation.


### -field WheaRawDataFormatGeneric

The raw data in the hardware error packet contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a> structure.


### -field WheaRawDataFormatMax

The maximum number of formats of raw hardware error data.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560476">WHEA_ERROR_PACKET_V1</a> structure contains a member of type WHEA_RAW_DATA_FORMAT that specifies the format of the raw data that is contained in the hardware error packet.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560476">WHEA_ERROR_PACKET_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a>
 

 

