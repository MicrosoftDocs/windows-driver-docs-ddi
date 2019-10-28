---
UID: NN:wudfusb.IWDFUsbTargetDevice
title: IWDFUsbTargetDevice (wudfusb.h)
description: The IWDFUsbTargetDevice interface exposes a USB device I/O target object.
old-location: wdf\iwdfusbtargetdevice.htm
tech.root: wdf
ms.assetid: 627a4633-6857-43a5-af2d-36e4e554ca83
ms.date: 02/26/2018
ms.keywords: IWDFUsbTargetDevice, IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface,described, UMDFUSBref_4ff51830-55c1-4e2c-b095-8ca88bd2e56f.xml, umdf.iwdfusbtargetdevice, wdf.iwdfusbtargetdevice, wudfusb/IWDFUsbTargetDevice
ms.topic: interface
f1_keywords:
 - "wudfusb/IWDFUsbTargetDevice"
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
- IWDFUsbTargetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetDevice interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>IWDFUsbTargetDevice</b> interface exposes a USB device I/O target object.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetDevice</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>. <b>IWDFUsbTargetDevice</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUsbTargetDevice</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-formatrequestforcontroltransfer">IWDFUsbTargetDevice::FormatRequestForControlTransfer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-formatrequestforcontroltransfer">FormatRequestForControlTransfer</a> method formats an I/O request object for a USB control transfer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getnuminterfaces">IWDFUsbTargetDevice::GetNumInterfaces</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getnuminterfaces">GetNumInterfaces</a> method retrieves the number of USB interfaces for the USB device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getwinusbhandle">IWDFUsbTargetDevice::GetWinUsbHandle</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-getwinusbhandle">GetWinUsbHandle</a> method retrieves the WinUsb interface handle that is associated with a I/O target device object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievedescriptor">IWDFUsbTargetDevice::RetrieveDescriptor</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievedescriptor">RetrieveDescriptor</a> method retrieves a USB descriptor, which can describe a device, configuration, or string.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievedeviceinformation">IWDFUsbTargetDevice::RetrieveDeviceInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievedeviceinformation">RetrieveDeviceInformation</a> method retrieves device information of the specified type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievepowerpolicy">IWDFUsbTargetDevice::RetrievePowerPolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrievepowerpolicy">RetrievePowerPolicy</a> method retrieves a WinUsb power policy.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface">IWDFUsbTargetDevice::RetrieveUsbInterface</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-retrieveusbinterface">RetrieveUsbInterface</a> method retrieves the specified USB interface for a USB device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-setpowerpolicy">IWDFUsbTargetDevice::SetPowerPolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetdevice-setpowerpolicy">SetPowerPolicy</a> method sets the WinUsb power policy.

</td>
</tr>
</table> 

