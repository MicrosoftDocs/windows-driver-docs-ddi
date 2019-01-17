---
UID: NS:ntddk._WHEA_ERROR_RECORD
title: "_WHEA_ERROR_RECORD"
description: The WHEA_ERROR_RECORD structure describes an error record that contains error information about a hardware error condition that occurred.
old-location: whea\whea_error_record.htm
tech.root: whea
ms.assetid: 29ed998c-d833-496f-a728-0eef2cd49ae6
ms.date: 02/20/2018
ms.keywords: "*PWHEA_ERROR_RECORD, PWHEA_ERROR_RECORD, PWHEA_ERROR_RECORD structure pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD, WHEA_ERROR_RECORD structure [WHEA Drivers and Applications], _WHEA_ERROR_RECORD, ntddk/PWHEA_ERROR_RECORD, ntddk/WHEA_ERROR_RECORD, whea.whea_error_record, whearef_dc309156-feee-4cc2-ba75-d39f3f05fa5f.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_ERROR_RECORD
product:
- Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_RECORD, WHEA_ERROR_RECORD, PWHEA_ERROR_RECORD"
---

# _WHEA_ERROR_RECORD structure


## -description


The WHEA_ERROR_RECORD structure describes an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that contains error information about a hardware error condition that occurred.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a> structure that describes general information about the hardware error condition.


### -field SectionDescriptor

A variable sized array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe each of the sections of error information that are contained in the error record. The number of structures in the array is specified by the <b>Header.SectionCount</b> member of the WHEA_ERROR_RECORD structure.


## -remarks



When a hardware error occurs, WHEA creates an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> to store the error information associated with the hardware error condition. Each error record is described by a WHEA_ERROR_RECORD structure. The Windows kernel includes the error record with the Event Tracing for Windows (ETW) hardware error event that it raises in response to the error so that the error record is saved in the system event log.

The format of the error records that are used by WHEA are based on the <i>Common Platform Error Record</i> as described in Appendix N of version 2.2 of the <a href="https://go.microsoft.com/fwlink/p/?linkid=69484">Unified Extensible Firmware Interface (UEFI) Specification</a>.

A user-mode application can retrieve the error record from the hardware error event for analysis. For more information about how to develop an application to retrieve error records from hardware error events, see <a href="https://msdn.microsoft.com/df1790ec-5a7f-41c2-94df-757621e67ade">WHEA Hardware Error Event Processing Applications</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560487">WHEA_ERROR_RECORD_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
 

 

