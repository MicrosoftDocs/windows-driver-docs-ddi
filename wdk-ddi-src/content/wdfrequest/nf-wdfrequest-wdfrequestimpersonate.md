---
UID: NF:wdfrequest.WdfRequestImpersonate
title: WdfRequestImpersonate function
description: The WdfRequestImpersonate method registers a driver-supplied event callback function that the framework should call for impersonation.
old-location: wdf\wdfrequestimpersonate.htm
tech.root: wdf
ms.assetid: E5267F04-D693-453B-BAD2-C61F89B07F6E
ms.date: 02/26/2018
ms.keywords: WdfRequestImpersonate, WdfRequestImpersonate method, wdf.wdfrequestimpersonate, wdfrequest/WdfRequestImpersonate
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfRequestImpersonate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestImpersonate function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfRequestImpersonate</b> method registers a driver-supplied event callback function  that the framework should call for impersonation.


## -parameters




### -param Request [in]

A handle to the framework request object that represents the I/O request that is being completed.


### -param ImpersonationLevel [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>-typed value that identifies the level of impersonation.


### -param EvtRequestImpersonate [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/FA3FE0C0-57EC-4761-991B-49CA65A79BDD">EvtRequestImpersonate</a> event callback function.


### -param Context [in, optional]

A pointer to a buffer that contains context information that is related to the impersonation call. The framework passes this context information in a call to the <a href="https://msdn.microsoft.com/FA3FE0C0-57EC-4761-991B-49CA65A79BDD">EvtRequestImpersonate</a> event callback function. This parameter is optional and can be <b>NULL</b>


## -returns



If the <b>WdfRequestImpersonate</b> method encounters no errors, it returns STATUS_SUCCESS.

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfRequestImpersonate</b> method does not return until the <a href="https://msdn.microsoft.com/FA3FE0C0-57EC-4761-991B-49CA65A79BDD">EvtRequestImpersonate</a> event callback function completes.

For more information, see <a href="https://msdn.microsoft.com/02EA93CE-3C4D-4F6F-8E58-DD78EBDB19DE">Handling Client Impersonation in UMDF Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/FA3FE0C0-57EC-4761-991B-49CA65A79BDD">EvtRequestImpersonate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>
 

 

