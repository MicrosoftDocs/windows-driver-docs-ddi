---
UID: NF:wdfrequest.WdfRequestImpersonate
title: WdfRequestImpersonate function
author: windows-driver-content
description: The WdfRequestImpersonate method registers a driver-supplied event callback function that the framework should call for impersonation.
old-location: wdf\wdfrequestimpersonate.htm
old-project: wdf
ms.assetid: E5267F04-D693-453B-BAD2-C61F89B07F6E
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfRequestImpersonate, WdfRequestImpersonate method, wdf.wdfrequestimpersonate, wdfrequest/WdfRequestImpersonate
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WUDFx02000.dll
apiname:
-	WdfRequestImpersonate
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestImpersonate function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestImpersonate</b> method registers a driver-supplied event callback function  that the framework should call for impersonation.


## -syntax


````
NTSTATUS WdfRequestImpersonate(
  _In_     WDFREQUEST                   Request,
  _In_     SECURITY_IMPERSONATION_LEVEL ImpersonationLevel,
  _In_     PFN_WDF_REQUEST_IMPERSONATE  EvtRequestImpersonate,
  _In_opt_ PVOID                        Context
);
````


## -parameters




### -param Request [in]

A handle to the framework request object that represents the I/O request that is being completed.


### -param ImpersonationLevel [in]

A <a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>-typed value that identifies the level of impersonation.


### -param EvtRequestImpersonate [in]

A pointer to the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_impersonate.md">EvtRequestImpersonate</a> event callback function.


### -param Context [in, optional]

A pointer to a buffer that contains context information that is related to the impersonation call. The framework passes this context information in a call to the <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_impersonate.md">EvtRequestImpersonate</a> event callback function. This parameter is optional and can be <b>NULL</b>


## -returns



If the <b>WdfRequestImpersonate</b> method encounters no errors, it returns STATUS_SUCCESS.

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfRequestImpersonate</b> method does not return until the <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_impersonate.md">EvtRequestImpersonate</a> event callback function completes.

For more information, see <a href="https://msdn.microsoft.com/02EA93CE-3C4D-4F6F-8E58-DD78EBDB19DE">Handling Client Impersonation in UMDF Drivers</a>.




## -see-also

<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_impersonate.md">EvtRequestImpersonate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestImpersonate method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

