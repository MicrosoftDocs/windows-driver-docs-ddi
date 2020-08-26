---
UID: NS:storport._STOR_LOG_EVENT_DETAILS
title: _STOR_LOG_EVENT_DETAILS (storport.h)
description: The STOR_LOG_EVENT_DETAILS structure provides details pertaining to Storport-specific error log events and system log events.
old-location: storage\stor_log_event_details.htm
tech.root: storage
ms.assetid: 2370e730-6c35-45e6-a370-62adc10df53b
ms.date: 03/29/2018
keywords: ["STOR_LOG_EVENT_DETAILS structure"]
ms.keywords: "*PSTOR_LOG_EVENT_DETAILS, PSTOR_LOG_EVENT_DETAILS, PSTOR_LOG_EVENT_DETAILS structure pointer [Storage Devices], STOR_LOG_EVENT_DETAILS, STOR_LOG_EVENT_DETAILS structure [Storage Devices], _STOR_LOG_EVENT_DETAILS, storage.stor_log_event_details, storport/PSTOR_LOG_EVENT_DETAILS, storport/STOR_LOG_EVENT_DETAILS, structs-storport_ba65fe62-1b9a-4234-b9a4-b145bf549699.xml"
f1_keywords:
 - "storport/STOR_LOG_EVENT_DETAILS"
 - "STOR_LOG_EVENT_DETAILS"
req.header: storport.h
req.include-header: Storport.h
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
- storport.h
api_name:
- STOR_LOG_EVENT_DETAILS
targetos: Windows
req.typenames: STOR_LOG_EVENT_DETAILS, *PSTOR_LOG_EVENT_DETAILS
---

# _STOR_LOG_EVENT_DETAILS structure


## -description


The <b>STOR_LOG_EVENT_DETAILS</b> structure provides details pertaining to Storport-specific error log events and system  log events.


## -struct-fields




### -field InterfaceRevision

The revision number of this interface. Set to STOR_CURRENT_LOG_INTERFACE_REVISION to use the version of the interface that matches this structure. Both the constant and the data structure are defined in the same header file. This member is set to 0x00000100 for the first revision.


### -field Size

The size of this structure. Set before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportlogsystemevent">StorPortLogSystemEvent</a>.


### -field Flags

Not currently used. Must be zero.


### -field EventAssociation

Specifies whether the event should be associated with the adapter, the target, or the LUN. For adapter- and target-associated events, the event is logged against the adapter's device object. For LUN-associated events, the event is logged against the LUN's device object if it exists; otherwise, it is logged against the adapter's device object.


### -field PathId

The SCSI path/bus corresponding to this event.


### -field TargetId

The SCSI target controller or device on the bus corresponding to this event.


### -field LunId

The SCSI logical unit number of the target device corresponding to this event.


### -field StorportSpecificErrorCode

If the <b>ErrorCode</b> value is specific to Storport and should be translated for use with IOLOGMSG.DLL, this value is set to <b>TRUE</b>. If the <b>ErrorCode</b> value is not specific to Storport and should be passed directly to the system event logging facility, this value is set to <b>FALSE</b>.


### -field ErrorCode

The event error code to log.


### -field UniqueId

Specifies a unique identifier associated with the ErrorCode. Often this is used as a location code, referencing the location in the miniport that triggered the event. This value is passed directly to the event logging facility.


### -field DumpDataSize

The size of the miniport-specific data block that is to be appended to the log entry. If no data block is to be written, this should be set to 0.


### -field DumpData

Pointer to the miniport-specific data block that is to be appended to the log entry. If no data block is to be written, DumpDataSize should be set to 0, and this field is ignored.


### -field StringCount

The count of null-terminated Unicode strings contained in the StringList member. If no strings are to be written, this should be set to 0.


### -field StringList

The list of null-terminated Unicode strings to be appended to the log entry for use in string substitution. These strings are substituted for the place holders "%2" through "%n" in the log message text when the log entry is being displayed. This list consists of an array of pointers to the null-terminated Unicode strings. StringCount contains the count of string pointers in this array, so no list termination entry is needed. If no strings are to be written, StringCount should be set to 0, and this field is ignored.


## -remarks



Although <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportlogerror">StorPortLogError</a> uses <b>PathId</b>, <b>TargetId</b>, and <b>LunId</b> values that are 8bits wide, for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportlogsystemevent">StorPortLogSystemEvent</a> they are 32bits wide. The combined size of the miniport driver's dump data and string areas cannot exceed 150 bytes. This restriction is due to the < 255 byte limit that the kernel enforces on the event log entries.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ne-storport-_stor_event_association_enum">STOR_EVENT_ASSOCIATION_ENUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportlogsystemevent">StorPortLogSystemEvent</a>
 

 

