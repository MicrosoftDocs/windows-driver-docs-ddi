---
UID: NS:ntddk._WHEA_ERROR_RECORD_HEADER
title: "_WHEA_ERROR_RECORD_HEADER"
author: windows-driver-content
description: The WHEA_ERROR_RECORD_HEADER structure describes general information about a hardware error condition.
old-location: whea\whea_error_record_header.htm
old-project: whea
ms.assetid: 2e6476c7-d096-4756-bebb-56fe559dce6d
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ntddk/WHEA_ERROR_RECORD_HEADER, whea.whea_error_record_header, whearef_25871c17-6a61-422d-ba94-d63b633c7f5a.xml, *PWHEA_ERROR_RECORD_HEADER, WHEA_ERROR_RECORD_HEADER structure [WHEA Drivers and Applications], WHEA_ERROR_RECORD_HEADER, _WHEA_ERROR_RECORD_HEADER, ntddk/PWHEA_ERROR_RECORD_HEADER, PWHEA_ERROR_RECORD_HEADER structure pointer [WHEA Drivers and Applications], PWHEA_ERROR_RECORD_HEADER
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
-	WHEA_ERROR_RECORD_HEADER
product: Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_RECORD_HEADER, WHEA_ERROR_RECORD_HEADER"
---

# _WHEA_ERROR_RECORD_HEADER structure


## -description


The WHEA_ERROR_RECORD_HEADER structure describes general information about a hardware error condition.


## -syntax


````
typedef struct _WHEA_ERROR_RECORD_HEADER {
  ULONG                              Signature;
  WHEA_REVISION                      Revision;
  ULONG                              SignatureEnd;
  USHORT                             SectionCount;
  WHEA_ERROR_SEVERITY                Severity;
  WHEA_ERROR_RECORD_HEADER_VALIDBITS ValidBits;
  ULONG                              Length;
  WHEA_TIMESTAMP                     Timestamp;
  GUID                               PlatformId;
  GUID                               PartitionId;
  GUID                               CreatorId;
  GUID                               NotifyType;
  ULONGLONG                          RecordId;
  WHEA_ERROR_RECORD_HEADER_FLAGS     Flags;
  WHEA_PERSISTENCE_INFO              PersistenceInfo;
  UCHAR                              Reserved[12];
} WHEA_ERROR_RECORD_HEADER, *PWHEA_ERROR_RECORD_HEADER;
````


## -struct-fields




### -field Signature

The signature of the error record. This member contains the value 'REPC'.


### -field Revision

A <a href="..\ntddk\ns-ntddk-_whea_revision.md">WHEA_REVISION</a> union that describes the revision level of the WHEA_ERROR_RECORD_HEADER structure.


### -field SignatureEnd

The end of the signature of the error record. This member contains the value 0xFFFFFFFF.


### -field SectionCount

The number of sections of error information that are contained in the error record.


### -field Severity

A <a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition described by the error record.


### -field ValidBits

A <a href="..\ntddk\ns-ntddk-_whea_error_record_header_validbits.md">WHEA_ERROR_RECORD_HEADER_VALIDBITS</a> union that specifies which members of the WHEA_ERROR_RECORD_HEADER structure contain valid data.


### -field Length

The length, in bytes, of the error record.


### -field Timestamp

A <a href="..\ntddk\ns-ntddk-_whea_timestamp.md">WHEA_TIMESTAMP</a> union that indicates the time that the error was reported to the operating system. This member contains valid data only if the <b>ValidBits.Timestamp</b> bit is set.


### -field PlatformId

A GUID that identifies the platform on which the hardware error occurred. This member contains valid data only if the <b>ValidBits.PlatformId</b> bit is set.


### -field PartitionId

A GUID that identifies the partition on which the hardware error occurred. This member contains valid data only if the <b>ValidBits.PartitionId</b> bit is set.


### -field CreatorId

A GUID that identifies the entity that created the error record. When the Windows kernel creates an error record, it sets this member to WHEA_RECORD_CREATOR_GUID.


### -field NotifyType

A GUID that identifies the notification mechanism by which an error condition is reported to the operating system. The following are the GUIDs for the standard notification types:





#### CMC_NOTIFY_TYPE_GUID

Corrected Machine Check (CMC)



#### CPE_NOTIFY_TYPE_GUID

Corrected Platform Error (CPE)



#### MCE_NOTIFY_TYPE_GUID

Machine Check Exception (MCE)



#### PCIe_NOTIFY_TYPE_GUID

PCI Express (PCIe) Error



#### INIT_NOTIFY_TYPE_GUID

INIT Error Record (INIT)



#### NMI_NOTIFY_TYPE_GUID

Nonmaskable Interrupt (NMI)



#### BOOT_NOTIFY_TYPE_GUID

Boot Error Record (BOOT)

For error notification types that do not conform to one of the standard types in the previous list, a platform-specific GUID can be defined to identify the notification mechanism. If the notification type does not correspond to any of the standard notification types or any platform-specific notification types, this member is set to GENERIC_NOTIFY_TYPE_GUID.


### -field RecordId

The identifier of the error record. This identifier is unique only on the system that created the error record.


### -field Flags

A WHEA_ERROR_RECORD_HEADER_FLAGS union that describes the error condition. The WHEA_ERROR_RECORD_HEADER_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_ERROR_RECORD_HEADER_FLAGS {
  struct {
    ULONG  Recovered:1;
    ULONG  PreviousError:1;
    ULONG  Simulated:1;
    ULONG  Reserved:29;
  };
  ULONG  AsULONG;
} WHEA_ERROR_RECORD_HEADER_FLAGS, *PWHEA_ERROR_RECORD_HEADER_FLAGS;</pre>
</td>
</tr>
</table></span></div>




#### Recovered

A single bit that indicates that the operating system recovered from the error condition.



#### PreviousError

A single bit that indicates that the error condition occurred in a previous session of the operating system.



#### Simulated

A single bit that indicates that the error condition was simulated.



#### Reserved

Reserved for system use.



#### AsULONG

A ULONG representation of the contents of the WHEA_ERROR_RECORD_HEADER_FLAGS union.


### -field PersistenceInfo

A <a href="..\ntddk\ns-ntddk-_whea_persistence_info.md">WHEA_PERSISTENCE_INFO</a> union that is used by the error record persistence interface.


### -field Reserved

Reserved for system use.


## -remarks



A WHEA_ERROR_RECORD_HEADER structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure. The WHEA_ERROR_RECORD_HEADER structure describes general information about the hardware error condition that is described by the error record.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_header_validbits.md">WHEA_ERROR_RECORD_HEADER_VALIDBITS</a>



<a href="..\ntddk\ns-ntddk-_whea_revision.md">WHEA_REVISION</a>



<a href="..\ntddk\ns-ntddk-_whea_persistence_info.md">WHEA_PERSISTENCE_INFO</a>



<a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>



<a href="..\ntddk\ns-ntddk-_whea_timestamp.md">WHEA_TIMESTAMP</a>



<a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_RECORD_HEADER structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

