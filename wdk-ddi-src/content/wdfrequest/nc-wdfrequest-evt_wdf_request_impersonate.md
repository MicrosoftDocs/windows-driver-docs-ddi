---
UID: NC:wdfrequest.EVT_WDF_REQUEST_IMPERSONATE
title: EVT_WDF_REQUEST_IMPERSONATE
author: windows-driver-content
description: A driver's EvtRequestImpersonate event callback function performs tasks at the requested impersonation level, such as opening a protected file.
old-location: wdf\evtrequestimpersonate.htm
old-project: wdf
ms.assetid: FA3FE0C0-57EC-4761-991B-49CA65A79BDD
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtrequestimpersonate, EvtRequestImpersonate callback function, EvtRequestImpersonate, EVT_WDF_REQUEST_IMPERSONATE, EVT_WDF_REQUEST_IMPERSONATE, wdfrequest/EvtRequestImpersonate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfrequest.h
apiname:
-	EvtRequestImpersonate
product: Windows
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_REQUEST_IMPERSONATE callback


## -description


<p class="CCE_Message">[Applies to UMDF only]

A driver's <i>EvtRequestImpersonate</i> event callback function performs tasks at the requested impersonation level, such as opening a protected file.


## -prototype


````
EVT_WDF_REQUEST_IMPERSONATE EvtRequestImpersonate;

void EvtRequestImpersonate(
  _In_     WDFREQUEST Request,
  _In_opt_ PVOID      Context
)
{ ... }
````


## -parameters




### -param Request [in]

A handle to a framework request object that represents the I/O request that requires impersonation.


### -param Context [in, optional]

A pointer to a context that was previously supplied in the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestimpersonate.md">WdfRequestImpersonate</a> method. This parameter is optional and can be NULL if a context is not required. 




## -returns


This callback function does not return a value.



## -remarks


User-Mode Driver Framework (UMDF) does not allow a driver's <i>EvtRequestImpersonate</i> callback function to call any of the framework's object methods. This ensures that the driver does not expose the impersonation level to other driver callback functions or other drivers.

For more information, see <a href="https://msdn.microsoft.com/02EA93CE-3C4D-4F6F-8E58-DD78EBDB19DE">Handling Client Impersonation in UMDF Drivers</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestimpersonate.md">WdfRequestImpersonate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_REQUEST_IMPERSONATE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

