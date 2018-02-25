---
UID: NF:wdfinterrupt.WdfInterruptDisable
title: WdfInterruptDisable function
author: windows-driver-content
description: The WdfInterruptDisable method disables a specified device interrupt by calling the driver's EvtInterruptDisable callback function.
old-location: wdf\wdfinterruptdisable.htm
old-project: wdf
ms.assetid: 8ece6a3f-2f25-4143-8f0e-c65c02794cc4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , D, DFInterruptObjectRef_05ca577a-87b3-419a-a3f8-ee57b0765701.xml, I, W, WdfInterruptDisable, WdfInterruptDisable method, a, b, d, e, f, i, kmdf.wdfinterruptdisable, l, n, p, r, s, t, u, wdf.wdfinterruptdisable, wdfinterrupt/WdfInterruptDisable"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
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
-	WdfInterruptDisable
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptDisable function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptDisable</b> method disables a specified device interrupt by calling the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function.


## -syntax


````
VOID WdfInterruptDisable(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Most framework-based drivers don't need to call <b>WdfInterruptDisable</b>, because the framework calls the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function each time the device leaves its working (D0) state.

For <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt objects</a>, the framework calls <b>WdfInterruptDisable</b> at PASSIVE_LEVEL.

Do not call <b>WdfInterruptDisable</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example disables the device interrupt that is associated with a specified interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfInterruptDisable(Interrupt);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a>



<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptenable.md">WdfInterruptEnable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptDisable method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

