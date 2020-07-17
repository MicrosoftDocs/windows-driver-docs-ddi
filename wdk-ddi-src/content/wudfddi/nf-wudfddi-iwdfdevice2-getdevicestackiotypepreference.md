---
UID: NF:wudfddi.IWDFDevice2.GetDeviceStackIoTypePreference
title: IWDFDevice2::GetDeviceStackIoTypePreference (wudfddi.h)
description: The GetDeviceStackIoTypePreference method retrieves the buffer access methods that the framework is using for a device.
old-location: wdf\iwdfdevice2_getdevicestackiotypepreference.htm
tech.root: wdf
ms.assetid: 3a1f6432-3f61-4502-ac98-fa984539f88e
ms.date: 02/26/2018
keywords: ["IWDFDevice2::GetDeviceStackIoTypePreference"]
ms.keywords: GetDeviceStackIoTypePreference, GetDeviceStackIoTypePreference method, GetDeviceStackIoTypePreference method,IWDFDevice2 interface, IWDFDevice2 interface,GetDeviceStackIoTypePreference method, IWDFDevice2.GetDeviceStackIoTypePreference, IWDFDevice2::GetDeviceStackIoTypePreference, UMDFDeviceObjectRef_f6402826-fe3b-46c7-a4a8-d1d4f74e4b5c.xml, umdf.iwdfdevice2_getdevicestackiotypepreference, wdf.iwdfdevice2_getdevicestackiotypepreference, wudfddi/IWDFDevice2::GetDeviceStackIoTypePreference
f1_keywords:
 - "wudfddi/IWDFDevice2.GetDeviceStackIoTypePreference"
 - "IWDFDevice2.GetDeviceStackIoTypePreference"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
- IWDFDevice2.GetDeviceStackIoTypePreference
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice2::GetDeviceStackIoTypePreference


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceStackIoTypePreference</b> method retrieves the buffer access methods that the framework is using for a device.


## -parameters




### -param ReadWritePreference [out]

A pointer to a driver-allocated location that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value. This value identifies the buffer access method that the framework is using for a device's read and write requests.


### -param IoControlPreference [out]

A pointer to a driver-allocated location that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value. This value that identifies the buffer access method that the framework is using for a device's I/O control requests.


## -remarks



If your driver calls <b>GetDeviceStackIoTypePreference</b> before the PnP manager has loaded all of the device's drivers, the values that <b>GetDeviceStackIoTypePreference</b> retrieves might not be the values that it actually uses.

For more information about how the framework chooses a buffer access method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">How UMDF Chooses a Buffer Access Method for an I/O Request</a>.


#### Examples

The following code example retrieves the buffer access methods that the framework is using for a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_IO_TYPE ReadWriteAccessMethod;
WDF_DEVICE_IO_TYPE IoControlAccessMethod;

Device2->GetDeviceStackIoTypePreference(&ReadWriteAccessMethod,
                                        &IoControlAccessMethod); </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdeviceinitialize2-setiotypepreference">IWDFDeviceInitialize2::SetIoTypePreference</a>
 

 

