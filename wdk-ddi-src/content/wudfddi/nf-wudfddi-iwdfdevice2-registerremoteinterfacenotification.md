---
UID: NF:wudfddi.IWDFDevice2.RegisterRemoteInterfaceNotification
title: IWDFDevice2::RegisterRemoteInterfaceNotification (wudfddi.h)
description: The RegisterRemoteInterfaceNotification method registers a driver to receive a notification when a specified device interface becomes available.
old-location: wdf\iwdfdevice2_registerremoteinterfacenotification.htm
tech.root: wdf
ms.assetid: 48e1fc20-03e7-42ef-b57c-9246a56df4ef
ms.date: 02/26/2018
keywords: ["IWDFDevice2::RegisterRemoteInterfaceNotification"]
ms.keywords: IWDFDevice2 interface,RegisterRemoteInterfaceNotification method, IWDFDevice2.RegisterRemoteInterfaceNotification, IWDFDevice2::RegisterRemoteInterfaceNotification, RegisterRemoteInterfaceNotification, RegisterRemoteInterfaceNotification method, RegisterRemoteInterfaceNotification method,IWDFDevice2 interface, UMDFDeviceObjectRef_2629392c-5f58-4e33-be77-3422267c6a4b.xml, umdf.iwdfdevice2_registerremoteinterfacenotification, wdf.iwdfdevice2_registerremoteinterfacenotification, wudfddi/IWDFDevice2::RegisterRemoteInterfaceNotification
f1_keywords:
 - "wudfddi/IWDFDevice2.RegisterRemoteInterfaceNotification"
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
- IWDFDevice2.RegisterRemoteInterfaceNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice2::RegisterRemoteInterfaceNotification


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RegisterRemoteInterfaceNotification</b> method registers a driver to receive a notification when a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> becomes available.


## -parameters




### -param pDeviceInterfaceGuid [in]

A pointer to a GUID that identifies a device interface.


### -param IncludeExistingInterfaces [in]

A Boolean value. If the driver sets this value to <b>TRUE</b>, the framework notifies the driver if the specified device interface becomes available after the driver calls <b>RegisterRemoteInterfaceNotification</b>, and it also notifies the driver if the device interface was available before the driver called <b>RegisterRemoteInterfaceNotification</b>. 

If the driver sets this value to <b>FALSE</b>, the framework notifies the driver only if the device interface becomes available after the driver calls <b>RegisterRemoteInterfaceNotification</b>.


## -returns



<b>RegisterRemoteInterfaceNotification</b> returns S_OK of the operation succeeds. Otherwise, this method returns another value that Winerror.h contains.




## -remarks



Your driver can call <b>RegisterRemoteInterfaceNotification</b> only if the callback interface that the driver previously passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackremoteinterfacenotification">IPnpCallbackRemoteInterfaceNotification</a> interface.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">IDriverEntry::OnDeviceAdd</a> callback function can register for notification of the arrival of a device interface.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
CMyDriver::OnDeviceAdd(
    __in IWDFDriver  *FxDriver,
    __in IWDFDeviceInitialize  *FxDeviceInit
    )
{
    CComPtr<IWDFDevice> fxDevice;
    HRESULT hr;

    //
    // Create a device object and obtain the IWDFDevice interface.
    //
    hr = FxDriver->CreateDevice(FxDeviceInit,
                                MyDeviceIUnknown,
                                &fxDevice);
    if (FAILED(hr)) goto Error;

    //
    // Obtain the IWDFDevice2 interface from IWDFDevice.
    //
    CComPtr<IWDFDevice2> fxDevice2;
    if (FAILED(hr)) goto Error;
    hr = fxDevice->QueryInterface(IID_PPV_ARGS(&fxDevice2));
    if (S_OK != hr) goto Error;
    //
    // Register for notification when a device interface
    // arrives.
    //
    hr = fxDevice2->RegisterRemoteInterfaceNotification(&GUID_DEVINTERFACE_TOASTER,
                                                        true);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>
 

 

