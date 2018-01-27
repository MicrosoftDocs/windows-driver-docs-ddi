---
UID: NF:wdfinterrupt.WdfInterruptGetDevice
title: WdfInterruptGetDevice function
author: windows-driver-content
description: The WdfInterruptGetDevice method returns a handle to the framework device object that is associated with a specified framework interrupt object.
old-location: wdf\wdfinterruptgetdevice.htm
old-project: wdf
ms.assetid: c1e7a9ce-5794-4ed0-bb30-e3e68b0251db
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFInterruptObjectRef_9c646459-e17b-434f-b313-d22f3a211c4e.xml, WdfInterruptGetDevice method, WdfInterruptGetDevice, wdf.wdfinterruptgetdevice, wdfinterrupt/WdfInterruptGetDevice, kmdf.wdfinterruptgetdevice
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
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DIRQL
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
-	WdfInterruptGetDevice
product: Windows
targetos: Windows
req.typenames: *PWDF_INTERRUPT_PRIORITY, WDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WdfInterruptGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptGetDevice</b> method returns a handle to the framework device object that is associated with a specified framework interrupt object.


## -syntax


````
WDFDEVICE WdfInterruptGetDevice(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns


<b>WdfInterruptGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.



## -see-also

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptGetDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

