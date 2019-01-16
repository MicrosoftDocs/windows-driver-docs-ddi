---
UID: NN:sti.IStiDevice
title: IStiDevice
description: This section describes the methods defined for the IStiDevice COM Interface. Method prototypes are contained in Sti.h.
old-location: image\istidevice_interface_methods.htm
tech.root: image
ms.assetid: 86ce412e-007b-4ea9-9c09-766eee543852
ms.date: 05/03/2018
ms.keywords: IStiDevice, IStiDevice interface [Imaging Devices], IStiDevice interface [Imaging Devices],described, image.istidevice_interface_methods, sti/IStiDevice, stifnc_ef9e9c06-e918-462c-92c0-f4b1605a0847.xml
ms.topic: interface
req.header: sti.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	sti.h
api_name:
-	IStiDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDevice interface


## -description


This section describes the methods defined for the <a href="https://msdn.microsoft.com/b026fb74-9ce6-4d4e-8a5b-402731904064">IStiDevice COM Interface</a>. Method prototypes are contained in <i>Sti.h</i>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IStiDevice</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IStiDevice</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IStiDevice</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::DeviceReset</b> method resets a still image device to a known state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/eee5c6d7-17a3-461f-85e0-17f6b7114b19">Diagnostic</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Diagnostic</b> method executes diagnostic tests on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/mt637428">Escape</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Escape</b> method sends a request for a vendor-specific I/O operation to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451391">GetCapabilities</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetCapabilities</b> method returns a still image device's capabilities.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/20ad609d-454a-4d43-a58e-184cbb8e8da7">GetLastError</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetLastError</b> method returns the last known error associated with a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/de2f8897-c75f-4c37-aecb-f36d0f9933f9">GetLastErrorInfo</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/dd073fde-d2ba-45c0-a52c-22e86718901a">GetLastNotificationData</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetLastNotificationData</b> method returns a description of the most recent event that occurred on a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406321">GetStatus</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::GetStatus</b> method returns a still image device's status information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Initialize</b> method initializes an instance of the COM object that defines the <b>IStiDevice</b> interface. <i>This method is for internal use only</i>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawWriteCommand</b> method sends command information to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawWriteData</b> method writes data to a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543765">IStiDevice::Release</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a>, and removes access to the object's interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/208d9dc3-736b-4684-b8d3-802f6df78142">LockDevice</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::LockDevice </b>method locks a device for exclusive use by the caller.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/fc6b46af-d3e3-4a49-a354-c0effee6a005">RawReadCommand</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawReadCommand</b> method reads command information from a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b4510fac-839b-4744-9525-2bf96c5c724e">RawReadData</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::RawReadData</b> method reads data from a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/6266b311-6846-4615-a686-b68b00001fe7">Subscribe</a>
</td>
<td align="left" width="63%">
The<b> IStiDevice::Subscribe</b> method registers the caller to receive notifications of device events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0bcd48c6-be8a-47af-9e34-a06ce572925c">UnLockDevice</a>
</td>
<td align="left" width="63%">
The <b>IStiDevice::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ee0bfafa-9f4b-4b4a-8b26-4bab81253500">UnSubscribe</a>
</td>
<td align="left" width="63%">
The<b> IStiDevice::UnSubscribe</b> method removes the caller from the list of applications registered to receive notification of device events.

</td>
</tr>
</table> 

