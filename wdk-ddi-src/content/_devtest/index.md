---
UID: TP:devtest
title: Driver test tools
ms.assetid: df82015f-ea9d-3150-8041-fb2c5ed17afc
ms.date: 09/18/2020
keywords: ["Driver test tools"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Driver test tools

## -description

Overview of the Driver test tools technology.

To develop Driver test tools, you need these headers:

 * [wpprecorder.h](../wpprecorder/index.md)

For the programming guide, see [Driver test tools](/windows-hardware/drivers/devtest).

## Macros

| Title   | Description   |
| ---- |:---- |
| [WppRecorderConfigure macro](../wpprecorder/nf-wpprecorder-wpprecorderconfigure.md) | The WppRecorderConfigure method enables or disables the default log to which WPP prints. |
| [WppRecorderDumpLiveDriverData macro](../wpprecorder/nf-wpprecorder-wpprecorderdumplivedriverdata.md) | The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log. |
| [WppRecorderGetTriageInfo macro](../wpprecorder/nf-wpprecorder-wpprecordergettriageinfo.md) | The WppRecorderGetTriageInfo. |
| [WppRecorderLinkCounters macro](../wpprecorder/nf-wpprecorder-wpprecorderlinkcounters.md) | The WppRecorderLinkCounters. |
| [WppRecorderLogCreate macro](../wpprecorder/nf-wpprecorder-wpprecorderlogcreate.md) | The WppRecorderLogCreate method creates a buffer to contain the recorder log. |
| [WppRecorderLogDelete macro](../wpprecorder/nf-wpprecorder-wpprecorderlogdelete.md) | The WppRecorderLogDelete method deletes the specified recorder log. |
| [WppRecorderLogSetIdentifier macro](../wpprecorder/nf-wpprecorder-wpprecorderlogsetidentifier.md) | The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log. |