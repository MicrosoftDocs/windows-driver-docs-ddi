---
UID: NA:wdtfsystemaction
ms.assetid: 132e3c9a-f3dc-3ba8-ba36-20d82a3b6b03
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdtfsystemaction.h header



This header is used by dtf. For more information, see
- [dtf](../_dtf/index.md)

Wdtfsystemaction.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWDTFSystemAction2 interface](nn-wdtfsystemaction-iwdtfsystemaction2.md) | Defines operations and properties that support driver testing. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWDTFSystemAction2::ConnectedStandby method](nf-wdtfsystemaction-iwdtfsystemaction2-connectedstandby.md) | Puts the system into Connected Standby state and exits Connected Standby state after the desired time has passed. This method only works on a computer that supports Always On Always Connected (AOAC). |
| [IWDTFSystemAction2::GetFirstSleepState method](nf-wdtfsystemaction-iwdtfsystemaction2-getfirstsleepstate.md) | Returns the first supported sleep state. |
| [IWDTFSystemAction2::GetNextSleepState method](nf-wdtfsystemaction-iwdtfsystemaction2-getnextsleepstate.md) | Returns the next supported sleep state. |
| [IWDTFSystemAction2::IsRestartedWithContext method](nf-wdtfsystemaction-iwdtfsystemaction2-isrestartedwithcontext.md) | Gets a value that indicates whether the test script was restarted for a specific context. |
| [IWDTFSystemAction2::PowerAnalyzeTraceByFile method](nf-wdtfsystemaction-iwdtfsystemaction2-poweranalyzetracebyfile.md) | Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. This method will only work on Windows 8 and above. |
| [IWDTFSystemAction2::PowerTracingEnd method](nf-wdtfsystemaction-iwdtfsystemaction2-powertracingend.md) | This method ends a power trace session. |
| [IWDTFSystemAction2::PowerTracingStart method](nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstart.md) | Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method is available starting with Windows 8. |
| [IWDTFSystemAction2::PowerTracingStartByFile method](nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstartbyfile.md) | Starts a trace session for power state transitions and saves the trace message file (.etl) using the specified path. This method is available starting with Windows 8. |
| [IWDTFSystemAction2::RebootRestart method](nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestart.md) | Restart the system and the current test. |
| [IWDTFSystemAction2::RebootRestartWithContext method](nf-wdtfsystemaction-iwdtfsystemaction2-rebootrestartwithcontext.md) | Reboots the system and restarts the test script with context data. |
| [IWDTFSystemAction2::Sleep method](nf-wdtfsystemaction-iwdtfsystemaction2-sleep.md) | Puts the system into the desired sleep state. |
| [IWDTFSystemAction2::get_Critical method](nf-wdtfsystemaction-iwdtfsystemaction2-get_critical.md) | Gets or sets a value that indicates whether the the system power state is critical. |
| [IWDTFSystemAction2::get_IsRestarted method](nf-wdtfsystemaction-iwdtfsystemaction2-get_isrestarted.md) | Gets a value that indicates whether the test script restarted as a result of a call to RebootRestart or RebootRestartWithContext. |
| [IWDTFSystemAction2::get_SleepWakeTimeInSeconds method](nf-wdtfsystemaction-iwdtfsystemaction2-get_sleepwaketimeinseconds.md) | Gets or sets the time in seconds when the system will wake from the sleep state. |
| [IWDTFSystemAction2::put_Critical method](nf-wdtfsystemaction-iwdtfsystemaction2-put_critical.md) | Gets or sets a value that indicates whether the the system power state is critical. |
| [IWDTFSystemAction2::put_SleepWakeTimeInSeconds method](nf-wdtfsystemaction-iwdtfsystemaction2-put_sleepwaketimeinseconds.md) | Gets or sets the time in seconds when the system will wake from the sleep state. |
