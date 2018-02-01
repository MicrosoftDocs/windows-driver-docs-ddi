---
UID: NE:ntddk._WHEA_ERROR_SEVERITY
title: "_WHEA_ERROR_SEVERITY"
author: windows-driver-content
description: The WHEA_ERROR_SEVERITY enumeration defines the possible severity levels of a hardware error condition.
old-location: whea\whea_error_severity.htm
old-project: whea
ms.assetid: 3b056910-dc33-4608-bb7d-a3f13bc546ca
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PWHEA_ERROR_SEVERITY, WheaErrSevRecoverable, PWHEA_ERROR_SEVERITY enumeration pointer [WHEA Drivers and Applications], PWHEA_ERROR_SEVERITY, WheaErrSevFatal, ntddk/WheaErrSevCorrected, whea.whea_error_severity, ntddk/WheaErrSevInformational, ntddk/WheaErrSevFatal, ntddk/WheaErrSevRecoverable, whearef_e9b0fee6-a6cf-4f61-a3b6-ef53553aa3ff.xml, ntddk/PWHEA_ERROR_SEVERITY, WheaErrSevCorrected, WheaErrSevInformational, WHEA_ERROR_SEVERITY enumeration [WHEA Drivers and Applications], ntddk/WHEA_ERROR_SEVERITY, _WHEA_ERROR_SEVERITY, WHEA_ERROR_SEVERITY"
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
-	WHEA_ERROR_SEVERITY
product: Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_SEVERITY, WHEA_ERROR_SEVERITY"
---

# _WHEA_ERROR_SEVERITY enumeration


## -description


The WHEA_ERROR_SEVERITY enumeration defines the possible severity levels of a hardware error condition.


## -syntax


````
typedef enum _WHEA_ERROR_SEVERITY { 
  WheaErrSevRecoverable    = 0,
  WheaErrSevFatal          = 1,
  WheaErrSevCorrected      = 2,
  WheaErrSevInformational  = 3
} WHEA_ERROR_SEVERITY, *PWHEA_ERROR_SEVERITY;
````


## -enum-fields




### -field WheaErrSevRecoverable

The error has not been corrected but might be recoverable.


### -field WheaErrSevFatal

The error has not been corrected and is fatal.


### -field WheaErrSevCorrected

The error has been corrected by the hardware or firmware.


### -field WheaErrSevInformational

An error has not occurred.
<div class="alert"><b>Note</b>  In versions of the WDK that were released prior to Windows 7, this value was named <b>WheaErrSevNone</b>.</div><div> </div>

## -remarks


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>, <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>, <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>, and <a href="..\ntddk\ns-ntddk-_whea_generic_error.md">WHEA_GENERIC_ERROR</a> structures each contain a member of type WHEA_ERROR_SEVERITY that specifies the severity of the error that is described by the structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>

<a href="..\ntddk\ns-ntddk-_whea_generic_error.md">WHEA_GENERIC_ERROR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_SEVERITY enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

