---
UID: NF:winsplp.ControlPrintProcessor
title: ControlPrintProcessor function
author: windows-driver-content
description: A print processor's ControlPrintProcessor function allows the spooler to control a print job.
old-location: print\controlprintprocessor.htm
old-project: print
ms.assetid: a0a19747-ab39-4606-a49b-78e5e056da32
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ControlPrintProcessor, spoolfnc_203120f1-7819-448e-9813-3aa2b24bfd7f.xml, winsplp/ControlPrintProcessor, ControlPrintProcessor function [Print Devices], print.controlprintprocessor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Nwprint.lib
-	Nwprint.dll
apiname: 
-	ControlPrintProcessor
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ControlPrintProcessor function


## -description


A print processor's <b>ControlPrintProcessor</b> function allows the spooler to control a print job.


## -syntax


````
BOOL ControlPrintProcessor(
  _In_ HANDLE hPrintProcessor,
  _In_ DWORD  Command
);
````


## -parameters




### -param hPrintProcessor [in]

Caller-supplied print processor handle. This is the handle returned by a previous call to <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a>.


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

Based on the value received for <i>Command</i>, the function should either pause, resume, or cancel the current job. The <b>ControlPrintProcessor</b> function can be called asynchronously while the print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function is executing. Thus some sort of synchronization technique must be employed, such as setting an internally-defined event object to pause a job and resetting the event object when the job is resumed. The <b>ControlPrintProcessor</b> function can quickly return after setting or resetting the event object, and PrintDocumentOnPrintProcessor can wait for the event to be in the proper state.



## -see-also

<a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a>

<a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20ControlPrintProcessor function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

