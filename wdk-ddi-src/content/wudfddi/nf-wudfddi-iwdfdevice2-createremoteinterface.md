---
UID: NF:wudfddi.IWDFDevice2.CreateRemoteInterface
title: IWDFDevice2::CreateRemoteInterface (wudfddi.h)
description: The CreateRemoteInterface method creates a remote interface object that represents a device interface.
old-location: wdf\iwdfdevice2_createremoteinterface.htm
tech.root: wdf
ms.assetid: fb2def4b-c027-465d-b734-20b4b83a6308
ms.date: 02/26/2018
ms.keywords: CreateRemoteInterface, CreateRemoteInterface method, CreateRemoteInterface method,IWDFDevice2 interface, IWDFDevice2 interface,CreateRemoteInterface method, IWDFDevice2.CreateRemoteInterface, IWDFDevice2::CreateRemoteInterface, UMDFDeviceObjectRef_772989d9-ec18-4672-abea-ee4abd00b6ee.xml, umdf.iwdfdevice2_createremoteinterface, wdf.iwdfdevice2_createremoteinterface, wudfddi/IWDFDevice2::CreateRemoteInterface
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFDevice2.CreateRemoteInterface"
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
- IWDFDevice2.CreateRemoteInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice2::CreateRemoteInterface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateRemoteInterface</b> method creates a remote interface object that represents a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>.


## -parameters




### -param pRemoteInterfaceInit [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremoteinterfaceinitialize">IWDFRemoteInterfaceInitialize</a> interface that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function received.


### -param pCallbackInterface [in, optional]

A pointer to an optional, driver-supplied callback interface. The <b>IUnknown::QueryInterface</b> method of this interface must return a pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iremoteinterfacecallbackevent">IRemoteInterfaceCallbackEvent</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iremoteinterfacecallbackremoval">IRemoteInterfaceCallbackRemoval</a> interfaces, if the driver supports those interfaces. This parameter is optional and can be <b>NULL</b>.


### -param ppRemoteInterface [out]

A pointer to a driver-supplied location that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremoteinterface">IWDFRemoteInterface</a> interface of the new remote interface object.


## -returns



<b>CreateRemoteInterface</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate memory failed.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.




## -remarks



If your driver calls <b>CreateRemoteInterface</b>, it must do so from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function.

For more information about <b>CreateRemoteInterface</b> and using device interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>



#### Examples

The following code example shows an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function that creates a remote interface object, creates a remote target object, and opens the remote target for I/O operations.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void 
STDMETHODCALLTYPE
CMyDevice::OnRemoteInterfaceArrival(
    __in IWDFRemoteInterfaceInitialize * FxRemoteInterfaceInit
    )
{
    HRESULT hr = S_OK;

    //
    // Create a new remote interface object and provide a callback 
    // object to handle remote interface events.
    //
    CComPtr<IWDFRemoteInterface> fxRemoteInterface;
    hr = m_FxDevice->CreateRemoteInterface(FxRemoteInterfaceInit, 
                                           MyRemoteInterfaceIUnknown, 
                                           &fxRemoteInterface);
    if (FAILED(hr)) goto Error;
    //
    // Create a new remote target object and provide a callback 
    // object to handle remote target events.
    //
    CComPtr<IWDFRemoteTarget> fxTarget;
    hr = m_FxDevice->CreateRemoteTarget(MyRemoteTargetIUnknown,
                                        fxRemoteInterface,
                                        &fxTarget);
    if (FAILED(hr)) goto Error;

    //
    // Open the remote interface with read/write access.
    //
    hr = FxTarget->OpenRemoteInterface(fxRemoteInterface, 
                                       NULL,
                                       GENERIC_READ | GENERIC_WRITE,
                                       NULL);
    if (FAILED(hr)) goto Error;
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice2">IWDFDevice2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-openremoteinterface">IWDFRemoteTarget::OpenRemoteInterface</a>
 

 

