---
UID: NN:wudfusb.IWDFUsbInterface
title: IWDFUsbInterface
author: windows-driver-content
description: The IWDFUsbInterface interface exposes a USB interface that a USB device exposes.
old-location: wdf\iwdfusbinterface.htm
old-project: wdf
ms.assetid: 90770016-1267-437e-af70-99741231dc29
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFUsbInterface, IWDFUsbInterface interface, IWDFUsbInterface interface, described, UMDFUSBref_d505d36b-9a59-452d-b35f-ceeff7a0b818.xml, umdf.iwdfusbinterface, wdf.iwdfusbinterface, wudfusb/IWDFUsbInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfusb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbInterface
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbInterface interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>IWDFUsbInterface</b> interface exposes a USB interface that a USB device exposes.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbInterface</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>. <b>IWDFUsbInterface</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUsbInterface</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560317">IWDFUsbInterface::GetConfiguredSettingIndex</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/0deccfee-34e3-47ee-b141-9758cffcd0c2">GetConfiguredSettingIndex</a> method retrieves the current setting index for a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/ae4cffc8-65db-452c-9b85-19752c32c421">GetInterfaceDescriptor</a> method retrieves a descriptor for a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560327">IWDFUsbInterface::GetInterfaceNumber</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/de8de14a-94a8-49e2-912a-9c174f5a2c74">GetInterfaceNumber</a> method retrieves the index of a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/60ec8b38-8ab2-45d8-92ab-5943fd9bba79">GetNumEndPoints</a> method retrieves the number of endpoints (pipes) on a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560337">IWDFUsbInterface::GetWinUsbHandle</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/31c23596-21b2-4fb2-96bd-5372fe2432ab">GetWinUsbHandle</a> method retrieves the WinUsb interface handle that is associated with a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560339">IWDFUsbInterface::RetrieveUsbPipeObject</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/abfaad6b-be42-4547-aa26-5b44e53118bc">RetrieveUsbPipeObject</a> method retrieves a USB pipe object for the specified pipe index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560343">IWDFUsbInterface::SelectSetting</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/c47b025b-1be9-4fdc-965a-a9a82a394177">SelectSetting</a> method selects the specified alternate setting on a USB interface.

</td>
</tr>
</table> 

