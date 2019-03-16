---
UID: NS:wdfio._WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
title: _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS (wdfio.h)
description: The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.
old-location: wdf\wdf_io_forward_progress_reserved_policy_settings.htm
tech.root: wdf
ms.assetid: 28ffe82f-79b6-4a00-b4fa-36df5df303a6
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_47fb2461-dada-4f4e-aba8-91759b3092ea.xml, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure, _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS, kmdf.wdf_io_forward_progress_reserved_policy_settings, wdf.wdf_io_forward_progress_reserved_policy_settings, wdfio/WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
ms.topic: struct
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
- wdfio.h
api_name:
- WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
---

# _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</b> structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.


## -struct-fields




### -field Policy


### -field Policy.ExaminePolicy


### -field Policy.ExaminePolicy.EvtIoWdmIrpForForwardProgress

A pointer to the driver's queue-specific <a href="https://msdn.microsoft.com/71974802-954d-4856-a32b-1dcc45c36ba5">EvtIoWdmIrpForForwardProgress</a> callback function.


## -remarks



The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</b> structure is used as a member type in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552364">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.



