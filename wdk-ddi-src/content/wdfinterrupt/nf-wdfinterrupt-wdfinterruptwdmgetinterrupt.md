---
UID: NF:wdfinterrupt.WdfInterruptWdmGetInterrupt
title: WdfInterruptWdmGetInterrupt function
author: windows-driver-content
description: The WdfInterruptWdmGetInterrupt method returns a pointer to the WDM interrupt object that is associated with a specified framework interrupt object.
old-location: wdf\wdfinterruptwdmgetinterrupt.htm
old-project: wdf
ms.assetid: b301e9f6-264d-43d9-a344-b34dcd659d04
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFInterruptObjectRef_72a56280-07d3-43c1-99f9-68dc3323fe86.xml, wdf.wdfinterruptwdmgetinterrupt, WdfInterruptWdmGetInterrupt method, wdfinterrupt/WdfInterruptWdmGetInterrupt, kmdf.wdfinterruptwdmgetinterrupt, WdfInterruptWdmGetInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DIRQL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfInterruptWdmGetInterrupt
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptWdmGetInterrupt function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfInterruptWdmGetInterrupt</b> method returns a pointer to the WDM interrupt object that is associated with a specified framework interrupt object.


## -syntax


````
PKINTERRUPT WdfInterruptWdmGetInterrupt(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



The <b>WdfInterruptWdmGetInterrupt</b> method returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure. This method returns <b>NULL</b> if it is called before the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a> callback function is called or after the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function returns.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The pointer that the <b>WdfInterruptWdmGetInterrupt</b> method returns is valid until the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function returns. 

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example obtains a pointer to the KINTERRUPT structure that is associated with a specified framework interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PKINTERRUPT  wdmInterrupt;

wdmInterrupt = WdfInterruptWdmGetInterrupt(Interrupt);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptWdmGetInterrupt method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

