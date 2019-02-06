---
UID: NE:ntddk._WHEA_ERROR_SEVERITY
title: _WHEA_ERROR_SEVERITY (ntddk.h)
description: The WHEA_ERROR_SEVERITY enumeration defines the possible severity levels of a hardware error condition.
old-location: whea\whea_error_severity.htm
tech.root: whea
ms.assetid: 3b056910-dc33-4608-bb7d-a3f13bc546ca
ms.date: 02/20/2018
ms.keywords: "*PWHEA_ERROR_SEVERITY, PWHEA_ERROR_SEVERITY, PWHEA_ERROR_SEVERITY enumeration pointer [WHEA Drivers and Applications], WHEA_ERROR_SEVERITY, WHEA_ERROR_SEVERITY enumeration [WHEA Drivers and Applications], WheaErrSevCorrected, WheaErrSevFatal, WheaErrSevInformational, WheaErrSevRecoverable, _WHEA_ERROR_SEVERITY, ntddk/PWHEA_ERROR_SEVERITY, ntddk/WHEA_ERROR_SEVERITY, ntddk/WheaErrSevCorrected, ntddk/WheaErrSevFatal, ntddk/WheaErrSevInformational, ntddk/WheaErrSevRecoverable, whea.whea_error_severity, whearef_e9b0fee6-a6cf-4f61-a3b6-ef53553aa3ff.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_ERROR_SEVERITY
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_SEVERITY, *PWHEA_ERROR_SEVERITY
---

# _WHEA_ERROR_SEVERITY enumeration


## -description


The WHEA_ERROR_SEVERITY enumeration defines the possible severity levels of a hardware error condition.


## -enum-fields




### -field WheaErrSevRecoverable

The error has not been corrected but might be recoverable.


### -field WheaErrSevFatal

The error has not been corrected and is fatal.


### -field WheaErrSevCorrected

The error has been corrected by the hardware or firmware.


### -field WheaErrSevInformational

An error has not occurred.

<div class="alert"><b>Note</b>  In versions of the WDK that were released prior to Windows 7, this value was named <b>WheaErrSevNone</b>.</div>
<div> </div>

## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a> structures each contain a member of type WHEA_ERROR_SEVERITY that specifies the severity of the error that is described by the structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560524">WHEA_GENERIC_ERROR</a>
 

 

