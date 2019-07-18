---
UID: NN:wudfddi.IPnpCallbackHardwareInterrupt
title: IPnpCallbackHardwareInterrupt (wudfddi.h)
description: The IPnpCallbackHardwareInterrupt interface supports interrupt-related Plug and Play and power management callback methods.
old-location: wdf\ipnpcallbackhardwareinterrupt.htm
tech.root: wdf
ms.assetid: C66A570A-EEAF-4D18-A834-B50576F51E29
ms.date: 02/26/2018
ms.keywords: IPnpCallbackHardwareInterrupt, IPnpCallbackHardwareInterrupt interface, IPnpCallbackHardwareInterrupt interface,described, umdf.ipnpcallbackhardwareinterrupt, wdf.ipnpcallbackhardwareinterrupt, wudfddi/IPnpCallbackHardwareInterrupt
ms.topic: interface
f1_keywords:
 - "wudfddi/IPnpCallbackHardwareInterrupt"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackHardwareInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardwareInterrupt interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

  The <b>IPnpCallbackHardwareInterrupt</b> interface supports interrupt-related Plug and Play and power management callback methods.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackHardwareInterrupt</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPnpCallbackHardwareInterrupt</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0entrypostinterruptsenabled">OnD0EntryPostInterruptsEnabled</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0entrypostinterruptsenabled">OnD0EntryPostInterruptsEnabled</a> event callback function performs device-specific operations that are required when the driver enables the device's hardware interrupts.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0exitpreinterruptsdisabled">OnD0ExitPreInterruptsDisabled</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardwareinterrupt-ond0exitpreinterruptsdisabled">OnD0ExitPreInterruptsDisabled</a> event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a>
 

 

