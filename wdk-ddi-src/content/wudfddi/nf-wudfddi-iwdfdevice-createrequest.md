---
UID: NF:wudfddi.IWDFDevice.CreateRequest
title: IWDFDevice::CreateRequest (wudfddi.h)
description: The CreateRequest method creates an unformatted request object.
old-location: wdf\iwdfdevice_createrequest.htm
tech.root: wdf
ms.assetid: 031ce604-9d6f-4fdd-bacc-d1897f260a14
ms.date: 02/26/2018
keywords: ["IWDFDevice::CreateRequest"]
ms.keywords: CreateRequest, CreateRequest method, CreateRequest method,IWDFDevice interface, IWDFDevice interface,CreateRequest method, IWDFDevice.CreateRequest, IWDFDevice::CreateRequest, UMDFDeviceObjectRef_9eb18b05-e5fc-48cf-907b-ed7d188eac4b.xml, umdf.iwdfdevice_createrequest, wdf.iwdfdevice_createrequest, wudfddi/IWDFDevice::CreateRequest
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDevice::CreateRequest
 - wudfddi/IWDFDevice::CreateRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice.CreateRequest
---

# IWDFDevice::CreateRequest


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateRequest</b> method creates an unformatted request object.

## -parameters

### -param pCallbackInterface 

[in, optional]
A pointer to the <b>IUnknown</b> interface that the framework uses to determine the object-related event callback functions that the driver subscribes to on the newly created request object. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification. If the driver passes a valid pointer, the framework will call <b>QueryInterface</b> on the <b>IUnknown</b> interface for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a> interface. If the framework obtains the driver's <b>IObjectCleanup</b> interface, the framework can subsequently call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a> method to notify the driver that the request object is cleaned up.

### -param pParentObject 

[in, optional]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a> interface for the parent object of the created I/O request object. If <b>NULL</b>, the device object becomes the default parent.

### -param ppRequest 

[out]
A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the new request object.

## -returns

<b>CreateRequest</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

Before a UMDF driver uses the request object that <b>CreateRequest</b> creates, the driver must format the request object. To format an I/O request object, the driver calls one of the following methods:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforioctl">IWDFIoTarget::FormatRequestForIoctl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforread">IWDFIoTarget::FormatRequestForRead</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforwrite">IWDFIoTarget::FormatRequestForWrite</a>


</li>
</ul>
If a driver calls <b>CreateRequest</b> to create a request object, it must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> for the request object. Instead, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a> when it has finished using the request object. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

If <b>NULL</b> is specified in the <i>pParentObject</i> parameter, the device object becomes the default parent object for the newly created I/O request object. If a UMDF driver creates an I/O request object that the driver uses with a specific I/O queue object or another I/O request object, the driver should set that queue or request object as the created request object's parent object. When the parent object is deleted, the created request object is deleted. 


#### Examples

The following code example shows how to create a request, format the request for reading, and send the request on.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
CUmdfHidDevice::SendInterruptPipeRead(
    VOID
    )
{
    CComPtr<IWDFDevice> wdfDevice;

    HRESULT hr;

    IWDFFile *pTargetFile = NULL;

    // Allocate a new WDF request to send on the interrupt pipe.
    GetWdfDevice(&wdfDevice);
    hr = wdfDevice->CreateRequest(
                                  static_cast<IObjectCleanup*>(this), 
                                  wdfDevice, 
                                  &m_InterruptReadRequest
                                  );

    if (SUCCEEDED(hr))
    {
        m_InterruptPipe->GetTargetFile(&pTargetFile);
        hr = m_InterruptPipe->FormatRequestForRead(
                                                   m_InterruptReadRequest,
                                                   pTargetFile,
                                                   m_ReadMemory,
                                                   NULL,
                                                   NULL
                                                   );
    }

    // Issue the read to the pipe.
    if (SUCCEEDED(hr))
    {
        hr = m_InterruptReadRequest->Send(m_InterruptPipe, 0, 0);
    }

    return hr;
}</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforioctl">IWDFIoTarget::FormatRequestForIoctl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforread">IWDFIoTarget::FormatRequestForRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforwrite">IWDFIoTarget::FormatRequestForWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>

