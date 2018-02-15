---
UID: NF:wudfddi.IWDFInterrupt.GetDevice
title: IWDFInterrupt::GetDevice method
author: windows-driver-content
description: The GetDevice method returns the framework device object interface for this interrupt object.
old-location: wdf\iwdfinterrupt_getdevice.htm
old-project: wdf
ms.assetid: 71C4E02F-B58A-46BA-A6A7-133D6CAF2A85
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: GetDevice method, IWDFInterrupt interface, IWDFInterrupt interface, GetDevice method, wudfddi/IWDFInterrupt::GetDevice, wdf.iwdfinterrupt_getdevice, umdf.iwdfinterrupt_getdevice, GetDevice, IWDFInterrupt, GetDevice method, IWDFInterrupt::GetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFInterrupt.GetDevice
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFInterrupt::GetDevice method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDevice</b> method returns the framework device object interface for this interrupt object.


## -syntax


````
IWDFDevice3* GetDevice();
````


## -parameters






## -returns



<b>GetDevice</b> returns a pointer to the framework device object interface.




## -remarks



For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::GetDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

