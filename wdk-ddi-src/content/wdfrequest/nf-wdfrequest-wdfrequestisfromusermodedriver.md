---
UID: NF:wdfrequest.WdfRequestIsFromUserModeDriver
title: WdfRequestIsFromUserModeDriver function (wdfrequest.h)
description: The WdfRequestIsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application.
old-location: wdf\wdfrequestisfromusermodedriver.htm
tech.root: wdf
ms.assetid: 2D2980D7-6675-4414-AA32-D8782526E039
ms.date: 02/26/2018
keywords: ["WdfRequestIsFromUserModeDriver function"]
ms.keywords: WdfRequestIsFromUserModeDriver, WdfRequestIsFromUserModeDriver method, wdf.wdfrequestisfromusermodedriver, wdfrequest/WdfRequestIsFromUserModeDriver
f1_keywords:
 - "wdfrequest/WdfRequestIsFromUserModeDriver"
 - "WdfRequestIsFromUserModeDriver"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- WUDFx02000.dll
api_name:
- WdfRequestIsFromUserModeDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestIsFromUserModeDriver function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfRequestIsFromUserModeDriver</b> method indicates whether an I/O request came from a user-mode driver or an application.



## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestIsFromUserModeDriver</b> returns <b>TRUE</b> if the specified I/O request is from a user-mode driver. The method returns <b>FALSE</b> if the current I/O request came from an application.




## -remarks



If your driver supports <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-drivers">kernel-mode clients</a>, it should call <b>WdfRequestIsFromUserModeDriver</b> only if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetrequestormode">WdfRequestGetRequestorMode</a> returns <b>WdfUserMode</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetrequestormode">WdfRequestGetRequestorMode</a>
 

 

