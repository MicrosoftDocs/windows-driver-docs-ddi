---
UID: NF:wdfverifier.WdfVerifierDbgBreakPoint
title: WdfVerifierDbgBreakPoint function
author: windows-driver-content
description: The WdfVerifierDbgBreakPoint function breaks into a kernel debugger, if a debugger is running.
old-location: wdf\wdfverifierdbgbreakpoint.htm
old-project: wdf
ms.assetid: 55b8a6de-f20b-4d2d-8235-4837bc4a0d7d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDebugRef_e59a7661-75d0-49ac-bac3-a5845cb78226.xml, WdfVerifierDbgBreakPoint, WdfVerifierDbgBreakPoint function, kmdf.wdfverifierdbgbreakpoint, wdf.wdfverifierdbgbreakpoint, wdfverifier/WdfVerifierDbgBreakPoint
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
-	WdfVerifierDbgBreakPoint
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_COMPLETION_PARAMS, *PWDF_USB_REQUEST_COMPLETION_PARAMS
req.product: Windows 10 or later.
---

# WdfVerifierDbgBreakPoint function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger, if a debugger is running.


## -syntax


````
VOID WdfVerifierDbgBreakPoint(void);
````


## -parameters






## -returns



None




## -remarks



The <b>WdfVerifierDbgBreakPoint</b> function breaks into a kernel debugger if one of the following is true:

<ul>
<li><b>DbgBreakOnError</b> is set to a non-zero value in the registry.</li>
<li><b>VerifierOn</b> is set to a non-zero value and <b>DbgBreakOnError</b> is not set.
								</li>
<li>Driver Verifier is enabled, the  driver was built with framework version 1.9 or later, and neither <b>VerifierOn</b> nor <b>DbgBreakOnError</b> is set.</li>
</ul>
For more information about registry entries that you can use to debug your driver, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/registry-values-for-debugging-kmdf-drivers">Registry Entries for Debugging Framework-Based Drivers</a>.

For more information about debugging your driver, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/debugging-driver-installation">Debugging a KMDF Driver</a>.


#### Examples

The following code example shows how a driver might handle a failure to obtain an I/O request's output buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>Status = WdfRequestRetrieveOutputMemory(
                                        Request,
                                        &amp;memory
                                        );
if( !NT_SUCCESS(Status) ) {
    KdPrint(("EvtIoRead could not get request memory buffer. Status: 0x%x\n",Status));
    WdfVerifierDbgBreakPoint();
    WdfRequestCompleteWithInformation(
                                      Request,
                                      Status,
                                      0L
                                      );
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfverifier\nf-wdfverifier-wdfverifierkebugcheck.md">WdfVerifierKeBugCheck</a>



 

 


