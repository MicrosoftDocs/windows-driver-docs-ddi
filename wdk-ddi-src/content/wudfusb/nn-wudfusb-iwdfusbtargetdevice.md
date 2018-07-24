---
UID: NN:wudfusb.IWDFUsbTargetDevice
title: IWDFUsbTargetDevice
author: windows-driver-content
description: The IWDFUsbTargetDevice interface exposes a USB device I/O target object.
old-location: wdf\iwdfusbtargetdevice.htm
tech.root: wdf
ms.assetid: 627a4633-6857-43a5-af2d-36e4e554ca83
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFUsbTargetDevice, IWDFUsbTargetDevice interface, IWDFUsbTargetDevice interface,described, UMDFUSBref_4ff51830-55c1-4e2c-b095-8ca88bd2e56f.xml, umdf.iwdfusbtargetdevice, wdf.iwdfusbtargetdevice, wudfusb/IWDFUsbTargetDevice
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
-	IWDFUsbTargetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetDevice interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>IWDFUsbTargetDevice</b> interface exposes a USB device I/O target object.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetDevice</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>. <b>IWDFUsbTargetDevice</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560363">IWDFUsbTargetDevice::FormatRequestForControlTransfer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/7f75fbaa-06e8-4c4d-b1ee-c89a55889295">FormatRequestForControlTransfer</a> method formats an I/O request object for a USB control transfer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560366">IWDFUsbTargetDevice::GetNumInterfaces</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/4da2f2b0-f2ad-465d-b63e-f11406d4c210">GetNumInterfaces</a> method retrieves the number of USB interfaces for the USB device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560369">IWDFUsbTargetDevice::GetWinUsbHandle</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/458cbe27-be75-49f4-9849-969d881e0cd2">GetWinUsbHandle</a> method retrieves the WinUsb interface handle that is associated with a I/O target device object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560374">IWDFUsbTargetDevice::RetrieveDescriptor</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/c97b399e-fb25-475a-a2a0-0cf4fb24433c">RetrieveDescriptor</a> method retrieves a USB descriptor, which can describe a device, configuration, or string.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560377">IWDFUsbTargetDevice::RetrieveDeviceInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/04e3dfba-3313-4575-9956-5b1861b8212a">RetrieveDeviceInformation</a> method retrieves device information of the specified type.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560379">IWDFUsbTargetDevice::RetrievePowerPolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/e15561e3-ba3d-4c65-bb6e-d90f3fab22af">RetrievePowerPolicy</a> method retrieves a WinUsb power policy.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560381">IWDFUsbTargetDevice::RetrieveUsbInterface</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/9dfa8686-a815-417c-9488-dd86de0e15a2">RetrieveUsbInterface</a> method retrieves the specified USB interface for a USB device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560385">IWDFUsbTargetDevice::SetPowerPolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/e1b31df0-d383-43a3-bf9f-8874689cbf58">SetPowerPolicy</a> method sets the WinUsb power policy.

</td>
</tr>
</table> 

