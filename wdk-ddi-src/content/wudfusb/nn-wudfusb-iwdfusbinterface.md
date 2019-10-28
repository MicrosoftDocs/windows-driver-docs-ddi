---
UID: NN:wudfusb.IWDFUsbInterface
title: IWDFUsbInterface (wudfusb.h)
description: The IWDFUsbInterface interface exposes a USB interface that a USB device exposes.
old-location: wdf\iwdfusbinterface.htm
tech.root: wdf
ms.assetid: 90770016-1267-437e-af70-99741231dc29
ms.date: 02/26/2018
ms.keywords: IWDFUsbInterface, IWDFUsbInterface interface, IWDFUsbInterface interface,described, UMDFUSBref_d505d36b-9a59-452d-b35f-ceeff7a0b818.xml, umdf.iwdfusbinterface, wdf.iwdfusbinterface, wudfusb/IWDFUsbInterface
ms.topic: interface
f1_keywords:
 - "wudfusb/IWDFUsbInterface"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUsbInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbInterface interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>IWDFUsbInterface</b> interface exposes a USB interface that a USB device exposes.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbInterface</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFUsbInterface</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getconfiguredsettingindex">IWDFUsbInterface::GetConfiguredSettingIndex</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getconfiguredsettingindex">GetConfiguredSettingIndex</a> method retrieves the current setting index for a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacedescriptor">IWDFUsbInterface::GetInterfaceDescriptor</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacedescriptor">GetInterfaceDescriptor</a> method retrieves a descriptor for a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacenumber">IWDFUsbInterface::GetInterfaceNumber</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getinterfacenumber">GetInterfaceNumber</a> method retrieves the index of a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getnumendpoints">IWDFUsbInterface::GetNumEndPoints</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getnumendpoints">GetNumEndPoints</a> method retrieves the number of endpoints (pipes) on a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getwinusbhandle">IWDFUsbInterface::GetWinUsbHandle</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-getwinusbhandle">GetWinUsbHandle</a> method retrieves the WinUsb interface handle that is associated with a USB interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-retrieveusbpipeobject">IWDFUsbInterface::RetrieveUsbPipeObject</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-retrieveusbpipeobject">RetrieveUsbPipeObject</a> method retrieves a USB pipe object for the specified pipe index.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-selectsetting">IWDFUsbInterface::SelectSetting</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbinterface-selectsetting">SelectSetting</a> method selects the specified alternate setting on a USB interface.

</td>
</tr>
</table> 

