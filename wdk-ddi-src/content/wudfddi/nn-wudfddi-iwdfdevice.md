---
UID: NN:wudfddi.IWDFDevice
title: IWDFDevice
author: windows-driver-content
description: The IWDFDevice interface exposes a device object, which is a representation of a device on the system.
old-location: wdf\iwdfdevice.htm
old-project: wdf
ms.assetid: b0f8a156-e0e0-48d1-9e23-4ac07795df07
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDevice, IWDFDevice interface, IWDFDevice interface, described, UMDFDeviceObjectRef_d0dc8041-1d51-457b-8632-e500bf4df724.xml, umdf.iwdfdevice, wdf.iwdfdevice, wudfddi/IWDFDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
-	IWDFDevice
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFDevice</b> interface exposes a device object, which is a representation of a device on the system.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDevice</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>. <b>IWDFDevice</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFDevice</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557006">IWDFDevice::AssignDeviceInterfaceState</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/466af310-f2a7-4bd7-b927-df644e2e9c24">AssignDeviceInterfaceState</a> method enables or disables the specified device interface instance for a device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557010">IWDFDevice::CommitPnpState</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/650ad98a-81e5-4ec8-b276-a5dc79366652">CommitPnpState</a> method commits the state of the Plug and Play (PnP) property (that is, turns on, turns off, or sets to the default state) that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a> method set.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557014">IWDFDevice::ConfigureRequestDispatching</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/b3318695-e9f2-480a-9133-9008ef0002b7">ConfigureRequestDispatching</a> method configures the queuing of I/O requests of the specified type to the specified I/O queue.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557016">IWDFDevice::CreateDeviceInterface</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/0a88cbb6-66be-4ef7-93da-27d7ce169779">CreateDeviceInterface</a> method creates an instance of a device interface class.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/54c19d8c-59eb-44b2-b406-8fe33cdfcd63">CreateIoQueue</a> method configures the default I/O queue that is associated with a device or creates a secondary I/O queue for the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557021">IWDFDevice::CreateRequest</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/031ce604-9d6f-4fdd-bacc-d1897f260a14">CreateRequest</a> method creates an unformatted request object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557023">IWDFDevice::CreateSymbolicLink</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/15984217-e789-457c-b20f-c3d51741f5d3">CreateSymbolicLink</a> method creates a symbolic link for the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558828">IWDFDevice::CreateWdfFile</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/b356e3ac-451d-4a10-94e2-d03fcf76cb29">CreateWdfFile</a> method creates a file object for a driver to use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558830">IWDFDevice::GetDefaultIoQueue</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/9e998e54-b4c9-41ed-bba8-6f11c013f681">GetDefaultIoQueue</a> method retrieves the interface of the default I/O queue for a device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558831">IWDFDevice::GetDefaultIoTarget</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/27bc5f1b-128d-486b-ae09-0356b1164ae0">GetDefaultIoTarget</a> method retrieves the interface of the default I/O target for a device instance.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558833">IWDFDevice::GetDriver</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/5d17d970-56b7-494a-aa7b-d60065ff06d8">GetDriver</a> method retrieves the interface to the parent driver object of a device instance.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558834">IWDFDevice::GetPnpState</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/7214a0e9-5519-4daa-bd2f-cc3c697dd867">GetPnpState</a> method determines whether the given Plug and Play (PnP) property of a device is on or off (or set to the default state).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558835">IWDFDevice::PostEvent</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/3df25c91-d421-48fe-958c-48bce3bc78b8">PostEvent</a> method asynchronously notifies applications that are waiting for the specified event from a driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558837">IWDFDevice::RetrieveDeviceInstanceId</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/224277b4-447f-4981-aabf-90a10322c0df">RetrieveDeviceInstanceId</a> method retrieves the identifier of an instance of a device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558841">IWDFDevice::RetrieveDeviceName</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/75304f5d-8a07-4db5-9f20-5764ff5d2ef6">RetrieveDeviceName</a> method retrieves the name of an underlying kernel-mode device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a property store interface that drivers can use to access the registry.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/3bd88ecd-7c7c-4ee9-8eb8-bc5653bd4ed0">SetPnpState</a> method turns on or off (or sets to the default state) the specified Plug and Play (PnP) property of a device.

</td>
</tr>
</table> 


## -remarks



Each device object has a parent driver object. When a new device arrives in the system, the framework calls the parent driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a> callback function to notify the driver about the arrival. The driver can then call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to receive a pointer to the <b>IWDFDevice</b> interface for the new device object. 



