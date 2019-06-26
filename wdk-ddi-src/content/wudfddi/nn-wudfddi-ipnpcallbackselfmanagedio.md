---
UID: NN:wudfddi.IPnpCallbackSelfManagedIo
title: IPnpCallbackSelfManagedIo (wudfddi.h)
description: The IPnpCallbackSelfManagedIo interface is a Plug and Play (PnP) and power management (PM) interface.
old-location: wdf\ipnpcallbackselfmanagedio.htm
tech.root: wdf
ms.assetid: 34971df0-4abc-41a1-8d2f-6e36df1daf20
ms.date: 02/26/2018
ms.keywords: IPnpCallbackSelfManagedIo, IPnpCallbackSelfManagedIo interface, IPnpCallbackSelfManagedIo interface,described, UMDFDeviceObjectRef_0f139c45-68eb-4429-ac90-675d7eddea5a.xml, umdf.ipnpcallbackselfmanagedio, wdf.ipnpcallbackselfmanagedio, wudfddi/IPnpCallbackSelfManagedIo
ms.topic: interface
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackSelfManagedIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackSelfManagedIo interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IPnpCallbackSelfManagedIo</b> interface is a Plug and Play (PnP) and power management (PM) interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackSelfManagedIo</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPnpCallbackSelfManagedIo</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPnpCallbackSelfManagedIo</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediocleanup">IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediocleanup">OnSelfManagedIoCleanup</a> method releases memory for a device's self-managed I/O operations, after the device is removed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagedioflush">IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagedioflush">OnSelfManagedIoFlush</a> method flushes the device for a device's self-managed I/O operations.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagedioinit">IPnpCallbackSelfManagedIo::OnSelfManagedIoInit</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagedioinit">OnSelfManagedIoInit</a> method initializes a device's self-managed I/O operations.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediorestart">IPnpCallbackSelfManagedIo::OnSelfManagedIoRestart</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediorestart">OnSelfManagedIoRestart</a> method restarts a device's self-managed I/O operations.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediostop">IPnpCallbackSelfManagedIo::OnSelfManagedIoStop</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediostop">OnSelfManagedIoStop</a> method is not used in the current version of the UMDF.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediosuspend">IPnpCallbackSelfManagedIo::OnSelfManagedIoSuspend</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediosuspend">OnSelfManagedIoSuspend</a> method suspends a device's self-managed I/O operations.

</td>
</tr>
</table> 


## -remarks



A driver registers the <b>IPnpCallbackSelfManagedIo</b> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 



