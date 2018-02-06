---
UID: NE:ntddk._WHEA_RAW_DATA_FORMAT
title: "_WHEA_RAW_DATA_FORMAT"
author: windows-driver-content
description: The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet.
old-location: whea\whea_raw_data_format.htm
old-project: whea
ms.assetid: 809f2d72-e769-48c1-9ecf-6fa9020f6cdb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WheaRawDataFormatPCIExpress, PWHEA_RAW_DATA_FORMAT enumeration pointer [WHEA Drivers and Applications], ntddk/WheaRawDataFormatMax, WheaRawDataFormatGeneric, ntddk/WheaRawDataFormatIA32MCA, WheaRawDataFormatPCIXDevice, whea.whea_raw_data_format, WHEA_RAW_DATA_FORMAT enumeration [WHEA Drivers and Applications], ntddk/PWHEA_RAW_DATA_FORMAT, ntddk/WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT, ntddk/WheaRawDataFormatIntel64MCA, ntddk/WheaRawDataFormatPCIXDevice, ntddk/WheaRawDataFormatNMIPort, ntddk/WheaRawDataFormatPCIXBus, WheaRawDataFormatIntel64MCA, WheaRawDataFormatNMIPort, WheaRawDataFormatIPFSalRecord, WheaRawDataFormatMemory, ntddk/WheaRawDataFormatMemory, WheaRawDataFormatMax, ntddk/WheaRawDataFormatGeneric, WheaRawDataFormatPCIXBus, ntddk/WheaRawDataFormatAMD64MCA, WheaRawDataFormatIA32MCA, _WHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT, WheaRawDataFormatAMD64MCA, ntddk/WheaRawDataFormatPCIExpress, whearef_9ecb0580-4372-40f3-93da-4f866ee6211f.xml, PWHEA_RAW_DATA_FORMAT, ntddk/WheaRawDataFormatIPFSalRecord
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_RAW_DATA_FORMAT
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# _WHEA_RAW_DATA_FORMAT enumeration


## -description


The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet.


## -syntax


````
typedef enum _WHEA_RAW_DATA_FORMAT { 
  WheaRawDataFormatIPFSalRecord  = 0x00,
  WheaRawDataFormatIA32MCA,
  WheaRawDataFormatIntel64MCA,
  WheaRawDataFormatAMD64MCA,
  WheaRawDataFormatMemory,
  WheaRawDataFormatPCIExpress,
  WheaRawDataFormatNMIPort,
  WheaRawDataFormatPCIXBus,
  WheaRawDataFormatPCIXDevice,
  WheaRawDataFormatGeneric,
  WheaRawDataFormatMax
} WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT;
````


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

The raw data in the hardware error packet contains a <a href="..\ntddk\ns-ntddk-_whea_generic_error.md">WHEA_GENERIC_ERROR</a> structure.


### -field WheaRawDataFormatMax

The maximum number of formats of raw hardware error data.


## -remarks


The <a href="..\ntddk\ns-ntddk-_whea_error_packet_v1.md">WHEA_ERROR_PACKET_V1</a> structure contains a member of type WHEA_RAW_DATA_FORMAT that specifies the format of the raw data that is contained in the hardware error packet.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_generic_error.md">WHEA_GENERIC_ERROR</a>

<a href="..\ntddk\ns-ntddk-_whea_error_packet_v1.md">WHEA_ERROR_PACKET_V1</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540659">HalQuerySystemInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_RAW_DATA_FORMAT enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

