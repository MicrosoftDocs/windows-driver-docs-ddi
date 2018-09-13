---
UID: NF:wdfverifier.WdfVerifierKeBugCheck
title: WdfVerifierKeBugCheck function
author: windows-driver-content
description: The WdfVerifierKeBugCheck function creates a bug check.
old-location: wdf\wdfverifierkebugcheck.htm
tech.root: wdf
ms.assetid: 3fa8ea3d-cca0-402d-a3a8-1281ad4231d4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDebugRef_05774709-97ed-4fcc-b0b2-9fdac9a34094.xml, WdfVerifierKeBugCheck, WdfVerifierKeBugCheck function, kmdf.wdfverifierkebugcheck, wdf.wdfverifierkebugcheck, wdfverifier/WdfVerifierKeBugCheck
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfVerifierKeBugCheck
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfVerifierKeBugCheck function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfVerifierKeBugCheck</b> function creates a bug check.


## -parameters




### -param BugCheckCode [in]

One of the <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check codes</a> that are defined in <i>Bugcodes.h</i>.


### -param BugCheckParameter1 [in]

For information about this parameter, see the specified bug check code's description.


### -param BugCheckParameter2 [in]

For information about this parameter, see the specified bug check code's description.


### -param BugCheckParameter3 [in]

For information about this parameter, see the specified bug check code's description.


### -param BugCheckParameter4 [in]

For information about this parameter, see the specified bug check code's description.


## -returns



None




## -remarks



If your Kernel-Mode Driver Framework (KMDF) driver calls <b>WdfVerifierKeBugCheck</b>, the operating system halts and displays a <a href="https://msdn.microsoft.com/8cc42643-e231-49dd-96b0-6cb528d5d7a9">blue screen</a> unless a <a href="https://msdn.microsoft.com/e2490442-9d90-454b-95e0-db8c5d7fa19a">debugger</a> is running.

If your  User-Mode Driver Framework (UMDF) driver (version 2.0 or later) calls <b>WdfVerifierKeBugCheck</b>, the framework does not use  the parameters that the driver supplies.   In this case, the framework breaks into the debugger if one is connected. If a debugger is not connected, the framework generates an exception, and the default UMDF exception handler creates a minidump file. For more information about unhandled exceptions in the driver host process, see <a href="https://msdn.microsoft.com/44e4e5df-d968-4973-8a36-e93c75320ff6">How UMDF Reports Errors</a>.

For more information about debugging your driver, see <a href="https://msdn.microsoft.com/e648a7c9-0fdc-477e-b1cd-bec5dd8f5386">Debugging WDF Drivers</a>.


#### Examples

The following code example creates a bug check that uses the <a href="https://msdn.microsoft.com/bc60b4b3-aded-4c67-bbaa-aad1b6b38d30">MULTIPLE_IRP_COMPLETE_REQUESTS</a> bug check code.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfVerifierKeBugCheck(
                      MULTIPLE_IRP_COMPLETE_REQUESTS,
                      (ULONG_PTR) irp,
                      (ULONG_PTR) srb,
                      0,
                      0
                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551164">WdfVerifierDbgBreakPoint</a>
 

 

