---
UID: NN:wudfddi.IPnpCallbackHardwareInterrupt
title: IPnpCallbackHardwareInterrupt
author: windows-driver-content
description: The IPnpCallbackHardwareInterrupt interface supports interrupt-related Plug and Play and power management callback methods.
old-location: wdf\ipnpcallbackhardwareinterrupt.htm
old-project: wdf
ms.assetid: C66A570A-EEAF-4D18-A834-B50576F51E29
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallbackHardwareInterrupt, IPnpCallbackHardwareInterrupt interface, IPnpCallbackHardwareInterrupt interface, described, umdf.ipnpcallbackhardwareinterrupt, wdf.ipnpcallbackhardwareinterrupt, wudfddi/IPnpCallbackHardwareInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IPnpCallbackHardwareInterrupt
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackHardwareInterrupt interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

  The <b>IPnpCallbackHardwareInterrupt</b> interface supports interrupt-related Plug and Play and power management callback methods.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackHardwareInterrupt</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPnpCallbackHardwareInterrupt</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPnpCallbackHardwareInterrupt</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439750">OnD0EntryPostInterruptsEnabled</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439750">OnD0EntryPostInterruptsEnabled</a> event callback function performs device-specific operations that are required when the driver enables the device's hardware interrupts.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439755">OnD0ExitPreInterruptsDisabled</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439755">OnD0ExitPreInterruptsDisabled</a> event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.

</td>
</tr>
</table> 


## -see-also

<a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackHardwareInterrupt interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

