---
UID: TP:devtest
ms.assetid: df82015f-ea9d-3150-8041-fb2c5ed17afc
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Driver test tools


Overview of the Driver test tools technology.

To develop Driver test tools, you need these headers:

 * [ntddk.h](..\ntddk\index.md)
 * [wdm.h](..\wdm\index.md)
 * [wpprecorder.h](..\wpprecorder\index.md)

For the programming guide, see [Driver test tools](https://docs.microsoft.com/en-us/windows-hardware/drivers/devtest).

## Functions

| Title   | Description   |
| ---- |:---- |
| [DbgBreakPoint function](..\wdm\nf-wdm-dbgbreakpoint.md) | The DbgBreakPoint routine breaks into the kernel debugger. |
| [DbgBreakPointWithStatus function](..\wdm\nf-wdm-dbgbreakpointwithstatus.md) | The DbgBreakPointWithStatus routine breaks into the kernel debugger and sends the value of Status to the debugger. |
| [DbgPrint function](..\wdm\nf-wdm-dbgprint.md) | The DbgPrint routine sends a message to the kernel debugger. |
| [DbgPrintEx function](..\wdm\nf-wdm-dbgprintex.md) | The DbgPrintEx routine sends a string to the kernel debugger if the conditions you specify are met. |
| [DbgPrompt function](..\ntddk\nf-ntddk-dbgprompt.md) | The DbgPrompt routine displays a caller-specified user prompt string on the kernel debugger's display device and obtains a user response string. |
| [EtwActivityIdControl function](..\wdm\nf-wdm-etwactivityidcontrol.md) | The EtwActivityIdControl function creates, queries, and sets the current activity identifier. |
| [EtwEventEnabled function](..\wdm\nf-wdm-etweventenabled.md) | The EtwEventEnabled function verifies whether an event is enabled. |
| [EtwProviderEnabled function](..\wdm\nf-wdm-etwproviderenabled.md) | The EtwProviderEnabled function verifies that a provider is enabled for event logging at a specified level and keyword. |
| [EtwRegister function](..\wdm\nf-wdm-etwregister.md) | The EtwRegister function registers the event provider and must be called before a provider can start tracing. |
| [EtwUnregister function](..\wdm\nf-wdm-etwunregister.md) | The EtwUnregister function unregisters the event provider and must be called before the provider exits. |
| [EtwWrite function](..\wdm\nf-wdm-etwwrite.md) | The EtwWrite function is a tracing function for publishing events in your kernel-mode driver code. |
| [EtwWriteEx function](..\wdm\nf-wdm-etwwriteex.md) | The EtwWriteEx function is a tracing function for publishing events that support filtering in your kernel-mode driver code. |
| [EtwWriteString function](..\wdm\nf-wdm-etwwritestring.md) | The EventWriteString function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement. |
| [EtwWriteTransfer function](..\wdm\nf-wdm-etwwritetransfer.md) | The EtwWriteTransfer function marks an event that links two activities together; this type of event is referred to as a transfer event. |
| [KdChangeOption function](..\wdm\nf-wdm-kdchangeoption.md) | The KdChangeOption routine accesses and changes state in the kernel that is related to kernel debugging. |
| [KdDisableDebugger function](..\wdm\nf-wdm-kddisabledebugger.md) | The KdDisableDebugger routine disables the kernel debugger. |
| [KdEnableDebugger function](..\wdm\nf-wdm-kdenabledebugger.md) | The KdEnableDebugger routine re-enables the kernel debugger after a call to the KdDisableDebugger routine disables the kernel debugger. |
| [KdRefreshDebuggerNotPresent function](..\wdm\nf-wdm-kdrefreshdebuggernotpresent.md) | The KdRefreshDebuggerNotPresent macro refreshes the value of the KD_DEBUGGER_NOT_PRESENT global kernel variable. |
| [PcwAddInstance function](..\wdm\nf-wdm-pcwaddinstance.md) | The PcwAddInstance function adds the specified instance of the counter set to the consumer buffer. |
| [PcwCloseInstance function](..\wdm\nf-wdm-pcwcloseinstance.md) | The PcwCloseInstance function closes the specified instance of the counter set. |
| [PcwCreateInstance function](..\wdm\nf-wdm-pcwcreateinstance.md) | The PcwCreateInstance function creates a new instance for the specified registered counter set. |
| [PcwRegister function](..\wdm\nf-wdm-pcwregister.md) | The PcwRegister function registers the caller as a provider of the specified counter set. |
| [PcwUnregister function](..\wdm\nf-wdm-pcwunregister.md) | The PcwUnregister function unregisters the provider of the specified counter set. |
| [RECORDER_CONFIGURE_PARAMS_INIT function](..\wpprecorder\nf-wpprecorder-recorder_configure_params_init.md) | The RECORDER_CONFIGURE_PARAMS_INIT function is used to initialize the RECORDER_CONFIGURE_PARAMS structure. |
| [RECORDER_LOG_CREATE_PARAMS_INIT function](..\wpprecorder\nf-wpprecorder-recorder_log_create_params_init.md) | The RECORDER_LOG_CREATE_PARAMS_INIT function is used to initialize the RECORDER_LOG_CREATE_PARAMS structure. |
| [RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER function](..\wpprecorder\nf-wpprecorder-recorder_log_create_params_init_append_pointer.md) | The RECORDER_LOG_CREATE_PARAMS_INIT_APPEND_POINTER method initializes the RECORDER_LOG_CREATE_PARAMS with the pointer to link logs. |
| [SeEtwWriteKMCveEvent function](..\wdm\nf-wdm-seetwwritekmcveevent.md) | The SeEtwWriteKMCveEvent function is a tracing function for publishing events when an attempted security vulnerability exploit is detected in your kernel-mode drivers. |
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
| [vDbgPrintEx function](..\wdm\nf-wdm-vdbgprintex.md) | The vDbgPrintEx routine sends a string to the kernel debugger if certain conditions are met. |
| [vDbgPrintExWithPrefix function](..\wdm\nf-wdm-vdbgprintexwithprefix.md) | The vDbgPrintExWithPrefix routine sends a string to the kernel debugger if certain conditions that you specify are met. This routine can append a prefix to debugger output to help organize debugging results. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [ETWENABLECALLBACK callback](..\wdm\nc-wdm-etwenablecallback.md) | The EtwEnableCallback function is an optional driver-supplied callback function that is used to receive enable or disable notifications. |
| [PCW_CALLBACK callback](..\wdm\nc-wdm-pcw_callback.md) | Providers can implement a PCW_CALLBACK function to receive notification when consumers perform certain actions, such as adding or removing counters from a query. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_PCW_CALLBACK_INFORMATION structure](..\wdm\ns-wdm-_pcw_callback_information.md) | The PCW_CALLBACK_INFORMATION union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the PcwCallback function. |
| [_PCW_COUNTER_DESCRIPTOR structure](..\wdm\ns-wdm-_pcw_counter_descriptor.md) | The PCW_COUNTER_DESCRIPTOR structure supplies details about the notification to send. |
| [_PCW_COUNTER_INFORMATION structure](..\wdm\ns-wdm-_pcw_counter_information.md) | The PCW_COUNTER_INFORMATION structure describes attributes that identify a specific instance of a counter set. |
| [_PCW_DATA structure](..\wdm\ns-wdm-_pcw_data.md) | The PCW_DATA structure describes the array of data blocks that are associated with an instance. |
| [_PCW_MASK_INFORMATION structure](..\wdm\ns-wdm-_pcw_mask_information.md) | The PCW_MASK_INFORMATION structure supplies details about the notification to send to the provider. This information is passed as part of the Info parameter to the PcwCallback function. This mask information is included in PCW_CALLBACK_INFORMATION. |
| [_PCW_REGISTRATION_INFORMATION structure](..\wdm\ns-wdm-_pcw_registration_information.md) | The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set. |
| [_RECORDER_CONFIGURE_PARAMS structure](..\wpprecorder\ns-wpprecorder-_recorder_configure_params.md) | The RECORDER_CONFIGURE_PARAMS structure is an input parameter to the WppRecorderConfigure method to enable or disable the default log to which WPP prints. |
| [_RECORDER_LOG_CREATE_PARAMS structure](..\wpprecorder\ns-wpprecorder-_recorder_log_create_params.md) | The RECORDER_LOG_CREATE_PARAMS structure is an input parameter to the WppRecorderLogCreate method. |
| [_WPP_TRIAGE_INFO structure](..\wpprecorder\ns-wpprecorder-_wpp_triage_info.md) | Used to locate the WPP log for WER reporting. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_PCW_CALLBACK_TYPE enumeration](..\wdm\ne-wdm-_pcw_callback_type.md) | The PCW_CALLBACK_TYPE enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the PcwCallback function. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [ASSERTMSG macro](..\wdm\nf-wdm-assertmsg.md) | ASSERTMSG tests an expression. If the expression is false, it breaks into the kernel debugger and sends it the specified message. |
| [KdBreakPointWithStatus macro](..\wdm\nf-wdm-kdbreakpointwithstatus.md) | The KdBreakPointWithStatus macro breaks into the kernel debugger and sends the value of Status to the debugger. |
| [KdPrint macro](..\wdm\nf-wdm-kdprint.md) | The KdPrint macro sends a message to the kernel debugger. |
| [KdPrintEx macro](..\wdm\nf-wdm-kdprintex.md) | The KdPrintEx macro sends a string to the kernel debugger if the conditions you specify are met.A call to KdPrintEx requires double parentheses. |
| [WppRecorderConfigure macro](..\wpprecorder\nf-wpprecorder-wpprecorderconfigure.md) | The WppRecorderConfigure method enables or disables the default log to which WPP prints. |
| [WppRecorderDumpLiveDriverData macro](..\wpprecorder\nf-wpprecorder-wpprecorderdumplivedriverdata.md) | The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log. |
| [WppRecorderGetTriageInfo macro](..\wpprecorder\nf-wpprecorder-wpprecordergettriageinfo.md) | The WppRecorderGetTriageInfo. |
| [WppRecorderLinkCounters macro](..\wpprecorder\nf-wpprecorder-wpprecorderlinkcounters.md) | The WppRecorderLinkCounters. |
| [WppRecorderLogCreate macro](..\wpprecorder\nf-wpprecorder-wpprecorderlogcreate.md) | The WppRecorderLogCreate method creates a buffer to contain the recorder log. |
| [WppRecorderLogDelete macro](..\wpprecorder\nf-wpprecorder-wpprecorderlogdelete.md) | The WppRecorderLogDelete method deletes the specified recorder log. |
| [WppRecorderLogSetIdentifier macro](..\wpprecorder\nf-wpprecorder-wpprecorderlogsetidentifier.md) | The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log. |
