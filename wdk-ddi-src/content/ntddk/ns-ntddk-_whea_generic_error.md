---
UID: NS:ntddk._WHEA_GENERIC_ERROR
title: "_WHEA_GENERIC_ERROR"
author: windows-driver-content
description: The WHEA_GENERIC_ERROR structure describes error status data for a generic error source.
old-location: whea\whea_generic_error.htm
old-project: whea
ms.assetid: 7d624645-0199-4376-b84a-83d7da3ba981
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_GENERIC_ERROR, PWHEA_GENERIC_ERROR, PWHEA_GENERIC_ERROR structure pointer [WHEA Drivers and Applications], WHEA_GENERIC_ERROR, WHEA_GENERIC_ERROR structure [WHEA Drivers and Applications], _WHEA_GENERIC_ERROR, ntddk/PWHEA_GENERIC_ERROR, ntddk/WHEA_GENERIC_ERROR, whea.whea_generic_error, whearef_60117ecc-4c3f-438f-aba2-cd2d4268df27.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_GENERIC_ERROR
product: Windows
targetos: Windows
req.typenames: WHEA_GENERIC_ERROR, *PWHEA_GENERIC_ERROR
---

# _WHEA_GENERIC_ERROR structure


## -description


The WHEA_GENERIC_ERROR structure describes error status data for a generic error source.


## -syntax


````
typedef struct _WHEA_GENERIC_ERROR {
  WHEA_GENERIC_ERROR_BLOCKSTATUS BlockStatus;
  ULONG                          RawDataOffset;
  ULONG                          RawDataLength;
  ULONG                          DataLength;
  WHEA_ERROR_SEVERITY            ErrorSeverity;
  UCHAR                          Data[1];
} WHEA_GENERIC_ERROR, *PWHEA_GENERIC_ERROR;
````


## -struct-fields




### -field BlockStatus

A <a href="..\ntddk\ns-ntddk-_whea_generic_error_blockstatus.md">WHEA_GENERIC_ERROR_BLOCKSTATUS</a> union that indicates what kind of error data is reported in the generic error status block.


### -field RawDataOffset

The offset, in bytes, from the beginning of the WHEA_GENERIC_ERROR structure to the beginning of the raw error data.


### -field RawDataLength

The length, in bytes, of the raw error data that is located at the offset specified in the <b>RawDataOffset</b> member.


### -field DataLength

The size, in bytes, of the error data contained in the <b>Data</b> member.


### -field ErrorSeverity

A <a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition.


### -field Data

A variable-sized buffer that contains the error data from the generic error source. This buffer contains the generic error status block followed by the raw error data.


## -remarks



A generic error source is described by a <a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a> structure. The <b>ErrStatusAddress</b> member of the WHEA_GENERIC_ERROR_DESCRIPTOR structure points to a register that contains the physical address of a WHEA_GENERIC_ERROR structure in firmware reserved memory. This WHEA_GENERIC_ERROR structure contains the error status data for the generic error source.

A WHEA_GENERIC_ERROR structure is included in the <b>RawData</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure whenever the <b>RawDataFormat </b>member of the WHEA_ERROR_PACKET structure contains <b>WheaRawDataFormatGeneric</b>.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md">WHEA_GENERIC_ERROR_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_generic_error_blockstatus.md">WHEA_GENERIC_ERROR_BLOCKSTATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_GENERIC_ERROR structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

