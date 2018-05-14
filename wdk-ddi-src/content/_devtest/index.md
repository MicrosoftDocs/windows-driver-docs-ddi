---
UID: TP:devtest
ms.assetid: df82015f-ea9d-3150-8041-fb2c5ed17afc
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Driver test tools

## -description

Overview of the Driver test tools technology.

To develop Driver test tools, you need these headers:

 * [lkmdtel.h](..\lkmdtel\index.md)
 * [wpprecorder.h](..\wpprecorder\index.md)

For the programming guide, see [Driver test tools](https://docs.microsoft.com/en-us/windows-hardware/drivers/devtest).

## Functions

| Title   | Description   |
| ---- |:---- |
| [RECORDER_CONFIGURE_PARAMS_INIT function](..\wpprecorder\nf-wpprecorder-recorder_configure_params_init.md) | The RECORDER_CONFIGURE_PARAMS_INIT function is used to initialize the RECORDER_CONFIGURE_PARAMS structure. |
| [RECORDER_LOG_CREATE_PARAMS_INIT function](..\wpprecorder\nf-wpprecorder-recorder_log_create_params_init.md) | The RECORDER_LOG_CREATE_PARAMS_INIT function is used to initialize the RECORDER_LOG_CREATE_PARAMS structure. |
| [RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function](..\wpprecorder\nf-wpprecorder-recorder_log_create_params_init_append_pointer.md) | The RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER method initializes the RECORDER_LOG_CREATE_PARAMS with the pointer to link logs. |
| [imp_WppRecorderConfigure function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderconfigure.md) | The WppRecorderConfigure method enables or disables the default log to which WPP prints. |
| [imp_WppRecorderDumpLiveDriverData function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderdumplivedriverdata.md) | The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log. |
| [imp_WppRecorderGetCounterHandle function](..\wpprecorder\nf-wpprecorder-imp_wpprecordergetcounterhandle.md) | The WppRecorderGetCounterHandle method. |
| [imp_WppRecorderGetTriageInfo function](..\wpprecorder\nf-wpprecorder-imp_wpprecordergettriageinfo.md) | The WppRecorderGetTriageInfo. |
| [imp_WppRecorderIsDefaultLogAvailable function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderisdefaultlogavailable.md) | The WppRecorderIsDefaultLogAvailable method determines whether the default log is available. |
| [imp_WppRecorderLinkCounters function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderlinkcounters.md) | The WppRecorderLinkCounters. |
| [imp_WppRecorderLogCreate function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogcreate.md) | The WppRecorderLogCreate method creates a buffer to contain the recorder log. |
| [imp_WppRecorderLogDelete function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogdelete.md) | The WppRecorderLogDelete method deletes the specified recorder log. |
| [imp_WppRecorderLogGetDefault function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderloggetdefault.md) | The WppRecorderLogGetDefault method gets a handle to the default recorder log. |
| [imp_WppRecorderLogSetIdentifier function](..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogsetidentifier.md) | The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_RECORDER_CONFIGURE_PARAMS structure](..\wpprecorder\ns-wpprecorder-_recorder_configure_params.md) | The RECORDER_CONFIGURE_PARAMS structure is an input parameter to the WppRecorderConfigure method to enable or disable the default log to which WPP prints. |
| [_RECORDER_LOG_CREATE_PARAMS structure](..\wpprecorder\ns-wpprecorder-_recorder_log_create_params.md) | The RECORDER_LOG_CREATE_PARAMS structure is an input parameter to the WppRecorderLogCreate method. |
| [_WPP_TRIAGE_INFO structure](..\wpprecorder\ns-wpprecorder-_wpp_triage_info.md) | Used to locate the WPP log for WER reporting. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [WppRecorderConfigure macro](..\wpprecorder\nf-wpprecorder-wpprecorderconfigure.md) | The WppRecorderConfigure method enables or disables the default log to which WPP prints. |
| [WppRecorderDumpLiveDriverData macro](..\wpprecorder\nf-wpprecorder-wpprecorderdumplivedriverdata.md) | The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log. |
| [WppRecorderGetTriageInfo macro](..\wpprecorder\nf-wpprecorder-wpprecordergettriageinfo.md) | The WppRecorderGetTriageInfo. |
| [WppRecorderLinkCounters macro](..\wpprecorder\nf-wpprecorder-wpprecorderlinkcounters.md) | The WppRecorderLinkCounters. |
| [WppRecorderLogCreate macro](..\wpprecorder\nf-wpprecorder-wpprecorderlogcreate.md) | The WppRecorderLogCreate method creates a buffer to contain the recorder log. |
| [WppRecorderLogDelete macro](..\wpprecorder\nf-wpprecorder-wpprecorderlogdelete.md) | The WppRecorderLogDelete method deletes the specified recorder log. |
| [WppRecorderLogSetIdentifier macro](..\wpprecorder\nf-wpprecorder-wpprecorderlogsetidentifier.md) | The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log. |
