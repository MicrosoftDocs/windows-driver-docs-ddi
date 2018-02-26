---
UID: NF:sti.IStillImageW.WriteToErrorLog
title: IStillImageW::WriteToErrorLog method
author: windows-driver-content
description: The IStillImage::WriteToErrorLog method writes a message to the still image error log.
old-location: image\istillimage_writetoerrorlog.htm
old-project: image
ms.assetid: 24795026-41bc-447e-812f-8fc3a1c573b9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, E, I, IStillImageW, IStillImageW interface [Imaging Devices], WriteToErrorLog method, IStillImageW::WriteToErrorLog, IStillImageW::WriteToErrorLogiwiade, L, S, T, W, WriteToErrorLog method [Imaging Devices], WriteToErrorLog method [Imaging Devices], IStillImageW interface, WriteToErrorLog,IStillImageW.WriteToErrorLog, a, e, g, i, image.istillimage_writetoerrorlog, l, m, o, r, sti/IStillImageW::WriteToErrorLog, stifnc_1f27ad38-72b2-4b5f-8bb1-3456bfbd207a.xml, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStillImageW.WriteToErrorLog
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::WriteToErrorLog method


## -description


The <b>IStillImage::WriteToErrorLog </b>method writes a message to the still image error log.


## -syntax


````
HRESULT WriteToErrorLog(
       DWORD   dwMessageType,
  [in] LPCWSTR pszMessage
);
````


## -parameters




### -param dwMessageType

Caller-supplied constant value representing the message type. The following values are defined in <i>Sti.h</i>:

STI_TRACE_INFORMATION

STI_TRACE_WARNING

STI_TRACE_ERROR


### -param pszMessage [in]

Caller-supplied pointer to the message string to be written to the log file.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The still image error log file is named <i>sti_trace.log</i> and is located in the Windows directory. Registry values determine which still image error types (informational, warning, or error) are written to the error log (see <a href="https://msdn.microsoft.com/cedc8afc-54c4-485e-989c-481fe30d899b">Nonmodifiable Registry Entries</a>).

Error messages should be reserved for critical error conditions, such as device hardware failures. Informational messages can be used for your own debugging purposes. Logged messages aren't visible to users, but they might be used by a support engineer to help debug a user's problems.

Before calling <b>IStillImage::WriteToErrorLog</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.



