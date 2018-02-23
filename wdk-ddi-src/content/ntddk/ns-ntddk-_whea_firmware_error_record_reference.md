---
UID: NS:ntddk._WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
title: "_WHEA_FIRMWARE_ERROR_RECORD_REFERENCE"
author: windows-driver-content
description: The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture.
old-location: whea\whea_firmware_error_record_reference.htm
old-project: whea
ms.assetid: 950a9b93-ef69-4075-9231-eb481a53c617
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure [WHEA Drivers and Applications], ntddk/PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, whearef_b43d8c6f-f768-47a1-9494-4a4bfac7d586.xml, PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_RECORD, *PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE, whea.whea_firmware_error_record_reference, PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure pointer [WHEA Drivers and Applications], ntddk/WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, WHEA_FIRMWARE_RECORD, _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_FIRMWARE_ERROR_RECORD_REFERENCE
product: Windows
targetos: Windows
req.typenames: WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE
---

# _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure


## -description


The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture.


## -syntax


````
typedef struct _WHEA_FIRMWARE_ERROR_RECORD_REFERENCE {
  UCHAR     Type;
  UCHAR     Reserved[7];
  ULONGLONG FirmwareRecordId;
} WHEA_FIRMWARE_ERROR_RECORD_REFERENCE, *PWHEA_FIRMWARE_ERROR_RECORD_REFERENCE;
````


## -struct-fields




### -field Type

The type of firmware error record. This member is always set to WHEA_FIRMWARE_RECORD_TYPE_IPFSAL.


### -field Reserved

Reserved for system use.


### -field FirmwareRecordId

The identifier of the firmware error record.


## -remarks



The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes the data that is contained in an Itanium processor firmware error record reference section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains an Itanium processor firmware error record reference section only if the <b>SectionType </b>member of one of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains FIRMWARE_ERROR_RECORD_REFERENCE_GUID.

The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure contains a reference to a SAL error record that was created by the system firmware. For more information about the format of a SAL error record, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

