---
UID: NF:wdfverifier.WdfVerifierKeBugCheck
title: WdfVerifierKeBugCheck function
author: windows-driver-content
description: The WdfVerifierKeBugCheck function creates a bug check.
old-location: wdf\wdfverifierkebugcheck.htm
old-project: wdf
ms.assetid: 3fa8ea3d-cca0-402d-a3a8-1281ad4231d4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfverifierkebugcheck, kmdf.wdfverifierkebugcheck, WdfVerifierKeBugCheck function, DFDebugRef_05774709-97ed-4fcc-b0b2-9fdac9a34094.xml, WdfVerifierKeBugCheck, wdfverifier/WdfVerifierKeBugCheck
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfverifier.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfVerifierKeBugCheck
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# WdfVerifierKeBugCheck function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfVerifierKeBugCheck</b> function creates a bug check.


## -syntax


````
VOID WdfVerifierKeBugCheck(
  _In_ ULONG     BugCheckCode,
  _In_ ULONG_PTR BugCheckParameter1,
  _In_ ULONG_PTR BugCheckParameter2,
  _In_ ULONG_PTR BugCheckParameter3,
  _In_ ULONG_PTR BugCheckParameter4
);
````


## -parameters




#### - BugCheckCode [in]

One of the <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a> that are defined in <i>Bugcodes.h</i>.


#### - BugCheckParameter1 [in]

For information about this parameter, see the specified bug check code's description.


#### - BugCheckParameter2 [in]

For information about this parameter, see the specified bug check code's description.


#### - BugCheckParameter3 [in]

For information about this parameter, see the specified bug check code's description.


#### - BugCheckParameter4 [in]

For information about this parameter, see the specified bug check code's description.


## -returns


None



## -remarks


If your Kernel-Mode Driver Framework (KMDF) driver calls <b>WdfVerifierKeBugCheck</b>, the operating system halts and displays a <a href="https://msdn.microsoft.com/8cc42643-e231-49dd-96b0-6cb528d5d7a9">blue screen</a> unless a <a href="https://msdn.microsoft.com/e2490442-9d90-454b-95e0-db8c5d7fa19a">debugger</a> is running.

If your  User-Mode Driver Framework (UMDF) driver (version 2.0 or later) calls <b>WdfVerifierKeBugCheck</b>, the framework does not use  the parameters that the driver supplies.   In this case, the framework breaks into the debugger if one is connected. If a debugger is not connected, the framework generates an exception, and the default UMDF exception handler creates a minidump file. For more information about unhandled exceptions in the driver host process, see <a href="https://msdn.microsoft.com/44e4e5df-d968-4973-8a36-e93c75320ff6">How UMDF Reports Errors</a>.

For more information about debugging your driver, see <a href="https://msdn.microsoft.com/e648a7c9-0fdc-477e-b1cd-bec5dd8f5386">Debugging WDF Drivers</a>.



## -see-also

<a href="..\wdfverifier\nf-wdfverifier-wdfverifierdbgbreakpoint.md">WdfVerifierDbgBreakPoint</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfVerifierKeBugCheck function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

