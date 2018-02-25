---
UID: NS:ntddk._WHEA_ERROR_RECORD
title: "_WHEA_ERROR_RECORD"
author: windows-driver-content
description: The WHEA_ERROR_RECORD structure describes an error record that contains error information about a hardware error condition that occurred.
old-location: whea\whea_error_record.htm
old-project: whea
ms.assetid: 29ed998c-d833-496f-a728-0eef2cd49ae6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , *, *PWHEA_ERROR_RECORD, ,, A, C, D, E, H, O, P, PWHEA_ERROR_RECORD, PWHEA_ERROR_RECORD structure pointer [WHEA Drivers and Applications], R, W, WHEA_ERROR_RECORD, WHEA_ERROR_RECORD structure [WHEA Drivers and Applications], _, _WHEA_ERROR_RECORD, ntddk/PWHEA_ERROR_RECORD, ntddk/WHEA_ERROR_RECORD, whea.whea_error_record, whearef_dc309156-feee-4cc2-ba75-d39f3f05fa5f.xml"
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
-	WHEA_ERROR_RECORD
product: Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_RECORD, *PWHEA_ERROR_RECORD, WHEA_ERROR_RECORD, PWHEA_ERROR_RECORD"
---

# _WHEA_ERROR_RECORD structure


## -description


The WHEA_ERROR_RECORD structure describes an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that contains error information about a hardware error condition that occurred.


## -syntax


````
typedef struct _WHEA_ERROR_RECORD {
  WHEA_ERROR_RECORD_HEADER             Header;
  WHEA_ERROR_RECORD_SECTION_DESCRIPTOR SectionDescriptor[ANYSIZE_ARRAY];
} WHEA_ERROR_RECORD, *PWHEA_ERROR_RECORD;
````


## -struct-fields




### -field Header

A <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a> structure that describes general information about the hardware error condition.


### -field SectionDescriptor

A variable sized array of <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe each of the sections of error information that are contained in the error record. The number of structures in the array is specified by the <b>Header.SectionCount</b> member of the WHEA_ERROR_RECORD structure.


## -remarks



When a hardware error occurs, WHEA creates an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> to store the error information associated with the hardware error condition. Each error record is described by a WHEA_ERROR_RECORD structure. The Windows kernel includes the error record with the Event Tracing for Windows (ETW) hardware error event that it raises in response to the error so that the error record is saved in the system event log.

The format of the error records that are used by WHEA are based on the <i>Common Platform Error Record</i> as described in Appendix N of version 2.2 of the <a href="http://go.microsoft.com/fwlink/p/?linkid=69484">Unified Extensible Firmware Interface (UEFI) Specification</a>.

A user-mode application can retrieve the error record from the hardware error event for analysis. For more information about how to develop an application to retrieve error records from hardware error events, see <a href="https://msdn.microsoft.com/df1790ec-5a7f-41c2-94df-757621e67ade">WHEA Hardware Error Event Processing Applications</a>.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_RECORD structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

