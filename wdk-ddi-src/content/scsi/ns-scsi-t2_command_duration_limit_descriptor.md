---
UID: NS:scsi._T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
tech.root: storage
title: T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the T2_COMMAND_DURATION_LIMIT_DESCRIPTOR structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: scsi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: T2_COMMAND_DURATION_LIMIT_DESCRIPTOR, *PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - _T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
f1_keywords:
 - _T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - scsi/_T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - scsi/PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - scsi/T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - _T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
---

## -description

The **T2_COMMAND_DURATION_LIMIT_DESCRIPTOR** structure describes the command duration limit (CDL) information that corresponds to one **T2CommandDurationLimitDescriptors** index in the [**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2a_subpage.md) and [**MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2b_subpage.md) structures.

## -struct-fields

### -field T2CDLUNITS

The time units for **MAX_INACTIVE_TIME**, **MAX_ACTIVE_TIME**, **COMMAND_DURATION_GUIDELINE**. The default value for **T2CDLUNITS** is the smallest value that the device server allows for time units. If a MODE SELECT
command attempts to set **T2CDLUNITS** to a value that is less than the minimum supported by the device, then the command can be terminated with CHECK CONDITION status, with the sense key set to ILLEGAL REQUEST, and the additional sense code set to INVALID FIELD IN PARAMETER LIST. **T2CDLUNITS** can be one of the following values.

| Value            | Meaning |
| -----            | ------- |
| 0h               | No value specified |
| 6h               | 500 nanoseconds    |
| 8h               | 1 microsecond      |
| Ah               | 10 milliseconds    |
| Eh               | 500 milliseconds   |
| All other values | Reserved           |

### -field Reserved

Reserved.

### -field Reserved1

Reserved.

### -field MAX_INACTIVE_TIME

Specifies an upper limit on the time that elapses from the time at which the SCSI Command Received transport protocol service indication is invoked until the time at which the
device server initiates actions to access, transfer, or act upon the specified data. If **T2CDLUNITS** is set to 0h, **MAX_INACTIVE_TIME** is ignored.

**MAX_INACTIVE_TIME** can be one of the following values.

| Value    | Meaning |
| -----    | ------- |
| Non-zero | Specifies the time upper limit, in **T2CDLUNITS**.
| 0        | No time upper limit is specified by this T2 CDL descriptor. |

### -field MAX_ACTIVE_TIME

Specifies an upper limit on the time that elapses from when the device server initiates actions to access, transfer, or act upon the specified data until the time the device server returns status for the command. If **T2CDLUNITS** is set to 0h, MAX_ACTIVE_TIME is ignored.

**MAX_ACTIVE_TIME** can be one of the following values.

| Value    | Meaning |
| -----    | ------- |
| Non-zero | Specifies the time upper limit,
in **T2CDLUNITS**. |
| 0        | No time upper limit is specified by this T2 CDL descriptor. |

### -field MAX_ACTIVE_TIME_POLICY

Specifies the policy action taken if the max active time limit is not met; that is if the time used to process a command exceeds the time specified by **MAX_ACTIVE_TIME**. **MAX_ACTIVE_TIME_POLICY** can be one of the following values.

| Value | Description |
| ----- | ----------- |
| 0h       | The device server should complete the command at the earliest possible time; that is, do nothing based on the max time limit not being met. |
| 1h to Ch | Reserved |
| Dh       | The device server should complete the command with GOOD status, with the sense key set to COMPLETED and the sense code set to DATA CURRENTLY UNAVAILABLE. |
| Eh       | The device server should terminate the command with CHECK CONDITION status, with the sense key set to ABORTED COMMAND, and the additional sense code set to COMMAND TIMEOUT DURING PROCESSING or COMMAND TIMEOUT DURING PROCESSING DUE TO ERROR RECOVERY. If the starting LBA contents have been transferred to the application client, then the device server can indicate the largest LBA for which a contiguous range of LBAs have been transferred to the application client starting with the starting LBA of the read command as described in SBC-4. |
| Fh       | The device server should terminate the command with CHECK CONDITION status, with the sense key set to ABORTED COMMAND, and the additional sense code set to COMMAND TIMEOUT DURING PROCESSING. |

### -field MAX_INACTIVE_TIME_POLICY

Specifies the policy action taken if the max inactive limit is not met; that is, the action to take if the time used to cause a command to become an enabled command exceeds the time specified by **MAX_INACTIVE_TIME**. **MAX_INACTIVE_TIME_POLICY** can be one of the following values.

| Value | Description |
| ----- | ----------- |
| 0h       | The device server should complete the command at the earliest possible time; that is, do nothing based on the max time limit not being met. |
| 1h to Ch | Reserved |
| Dh       | The device server should complete the command with GOOD status, with the sense key set to COMPLETED and the sense code set to DATA CURRENTLY UNAVAILABLE. |
| Eh       | Reserved |
| Fh       | The device server shall terminate the command with CHECK CONDITION status, with the sense key set to ABORTED COMMAND and the additional sense code set to COMMAND TIMEOUT BEFORE PROCESSING. |

### -field Reserved2

Reserved.

### -field COMMAND_DURATION_GUIDELINE

Specifies the preferred length of time for the completion of a command. The device server processes this preferred duration based on comparisons to the
preferred duration for commands that select other CDL descriptors in which the
**COMMAND_DURATION_GUIDELINE** is not set to zero.

The preferred length of time for command completion is specified as the non-zero time to be added to fastest time for completion of a read command for which the device
server is able to return the requested data only by accessing the media. If **T2CDLUNITS** is set to 0h, the
**COMMAND_DURATION_GUIDELINE** is ignored.

The length of time in which the device server completes commands that select a T2 CDL descriptor must be both:

* Faster for smaller command duration guideline values.
* Slower for larger command duration guideline values, in comparison to the command duration guideline values specified by other CDL descriptors.

Additionally, larger magnitudes of the difference between the command duration guideline values in two different
T2 CDL descriptors must result in larger probabilities of differences between the length of time of command completions for commands that select those descriptors.

If **COMMAND_DURATION_GUIDELINE** is set to zero, no command completion guidance is provided by this T2 command duration limits descriptor.

The value of [**PerfvsComandDurationGuidelines**](ns-scsi-mode_command_duration_limit_page_t2a_subpage.md) might affect the timing relationships between the processing commands based on the specified command duration guideline
and the value of **COMMAND_DURATION_GUIDELINE_POLICY**.

**COMMAND_DURATION_GUIDELINE** interacts with the processing of **COMMAND_DURATION_GUIDELINE_POLICY**.

### -field Reserved3

Reserved.

### -field COMMAND_DURATION_GUIDELINE_POLICY

Specifies the policy action taken if a non-zero
**COMMAND_DURATION_GUIDELINE** value specifies a command duration guideline that the device cannot achieve for a command. Possible values follow.

| Value | Meaning |
| ----- | ------- |
| 0h      | The device server completes that command at the earliest possible time consistent with the specified **COMMAND_DURATION_GUIDELINE**. |
| 1h      | If **COMMAND_DURATION_GUIDELINE** has not been achieved and **COMMAND_DURATION_GUIDELINE_POLICY** is not in the seventh T2 command duration limits descriptor, then the device server continues to process that command using the command duration limits descriptor that has the next higher number. If **COMMAND DURATION GUIDELINE POLICY** is set to 1h in the seventh T2 command duration limits descriptor, then the device server terminates the MODE SELECT command with CHECK CONDITION status, with the sense key set to ILLEGAL REQUEST, and the additional sense code set to INVALID FIELD IN PARAMETER LIST. |
| 2h      | The device server continues processing that command as with no command duration limits descriptor being used. If **COMMAND DURATION GUIDELINE POLICY** is set to 2h in the seventh T2 command duration limits descriptor, then the device server terminates the MODE SELECT command with CHECK CONDITION status, with the sense key set to ILLEGAL REQUEST, and the additional sense code set to INVALID FIELD IN PARAMETER LIST. |
| 3h to Ch | Reserved |
| Dh       | The device server completes that command with GOOD status, with the sense key set to COMPLETED and the sense code set to DATA CURRENTLY UNAVAILABLE.
| Eh       | Reserved |
| Fh       | The device server terminates that command with CHECK CONDITION status, with the sense key set to ABORTED COMMAND and the additional sense code set to COMMAND TIMEOUT BEFORE PROCESSING. |

### -field Reserved4

Reserved.

### -field BypassSequestration

The bypass sequestration bit. This member is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
|  0    | The device server processes a command
associated with this T2 command duration limit descriptor as a non-sequestered command or a sequestered
command as described in 5.16 of the specification. |
|  1    | The device server processes a command associated with this T2 command duration limit descriptor as a non-sequestered command. |

### -field Reserved5

Reserved.

### -field Reserved6

Reserved.

## -remarks

See Table 459 in Section 7.5.11.2 of the T10 SCSI Primary Commands specification for additional details.

## -see-also

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2a_subpage.md)

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2b_subpage.md)
