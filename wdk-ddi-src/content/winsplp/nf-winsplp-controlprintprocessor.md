---
UID: NF:winsplp.ControlPrintProcessor
title: ControlPrintProcessor function (winsplp.h)
description: A print processor's ControlPrintProcessor function allows the spooler to control a print job.
old-location: print\controlprintprocessor.htm
tech.root: print
ms.assetid: a0a19747-ab39-4606-a49b-78e5e056da32
ms.date: 04/20/2018
keywords: ["ControlPrintProcessor function"]
ms.keywords: ControlPrintProcessor, ControlPrintProcessor function [Print Devices], print.controlprintprocessor, spoolfnc_203120f1-7819-448e-9813-3aa2b24bfd7f.xml, winsplp/ControlPrintProcessor
f1_keywords:
 - "winsplp/ControlPrintProcessor"
 - "ControlPrintProcessor"
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
req.lib: Nwprint.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Nwprint.lib
- Nwprint.dll
api_name:
- ControlPrintProcessor
product:
- Windows
targetos: Windows
req.typenames: 
---

# ControlPrintProcessor function


## -description


A print processor's <b>ControlPrintProcessor</b> function allows the spooler to control a print job.


## -parameters




### -param hPrintProcessor [in]

Caller-supplied print processor handle. This is the handle returned by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a>.


### -param Command [in]

Caller-supplied command indicating the type of operation to perform. The following commands are valid:

<table>
<tr>
<th>Command</th>
<th>Definition</th>
</tr>
<tr>
<td>
JOB_CONTROL_CANCEL

</td>
<td>
The function should cancel the current print job.

</td>
</tr>
<tr>
<td>
JOB_CONTROL_PAUSE

</td>
<td>
The function should pause the current print job.

</td>
</tr>
<tr>
<td>
JOB_CONTROL_RESUME

</td>
<td>
The function should resume the current print job.

</td>
</tr>
</table>
 


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. If the operation fails, the function should call SetLastError to set an error code, and then return <b>FALSE</b>.




## -remarks



Print processors are required to export a <b>ControlPrintProcessor</b> function. The spooler calls the function when an application calls the SetJob function, described in the Microsoft Windows SDK documentation.

Based on the value received for <i>Command</i>, the function should either pause, resume, or cancel the current job. The <b>ControlPrintProcessor</b> function can be called asynchronously while the print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function is executing. Thus some sort of synchronization technique must be employed, such as setting an internally-defined event object to pause a job and resetting the event object when the job is resumed. The <b>ControlPrintProcessor</b> function can quickly return after setting or resetting the event object, and PrintDocumentOnPrintProcessor can wait for the event to be in the proper state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a>
 

 

