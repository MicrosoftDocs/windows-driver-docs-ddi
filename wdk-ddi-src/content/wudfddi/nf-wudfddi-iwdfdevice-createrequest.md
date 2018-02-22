---
UID: NF:wudfddi.IWDFDevice.CreateRequest
title: IWDFDevice::CreateRequest method
author: windows-driver-content
description: The CreateRequest method creates an unformatted request object.
old-location: wdf\iwdfdevice_createrequest.htm
old-project: wdf
ms.assetid: 031ce604-9d6f-4fdd-bacc-d1897f260a14
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFDevice::CreateRequest, IWDFDevice, CreateRequest, wudfddi/IWDFDevice::CreateRequest, wdf.iwdfdevice_createrequest, UMDFDeviceObjectRef_9eb18b05-e5fc-48cf-907b-ed7d188eac4b.xml, CreateRequest method, IWDFDevice interface, IWDFDevice interface, CreateRequest method, CreateRequest method, umdf.iwdfdevice_createrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDevice.CreateRequest
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::CreateRequest method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateRequest</b> method creates an unformatted request object.


## -syntax


````
HRESULT CreateRequest(
  [in, optional] IUnknown      *pCallbackInterface,
  [in, optional] IWDFObject    *pParentObject,
  [out]          IWDFIoRequest **ppRequest
);
````


## -parameters




### -param pCallbackInterface [in, optional]

A pointer to the <b>IUnknown</b> interface that the framework uses to determine the object-related event callback functions that the driver subscribes to on the newly created request object. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification. If the driver passes a valid pointer, the framework will call <b>QueryInterface</b> on the <b>IUnknown</b> interface for the <a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a> interface. If the framework obtains the driver's <b>IObjectCleanup</b> interface, the framework can subsequently call the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> method to notify the driver that the request object is cleaned up. 


### -param pParentObject [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a> interface for the parent object of the created I/O request object. If <b>NULL</b>, the device object becomes the default parent. 


### -param ppRequest [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the new request object.


## -returns



<b>CreateRequest</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Before a UMDF driver uses the request object that <b>CreateRequest</b> creates, the driver must format the request object. To format an I/O request object, the driver calls one of the following methods:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559230">IWDFIoTarget::FormatRequestForIoctl</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>


</li>
</ul>
If a driver calls <b>CreateRequest</b> to create a request object, it must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> for the request object. Instead, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a> when it has finished using the request object. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

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
    CComPtr&lt;IWDFDevice&gt; wdfDevice;

    HRESULT hr;

    IWDFFile *pTargetFile = NULL;

    // Allocate a new WDF request to send on the interrupt pipe.
    GetWdfDevice(&amp;wdfDevice);
    hr = wdfDevice-&gt;CreateRequest(
                                  static_cast&lt;IObjectCleanup*&gt;(this), 
                                  wdfDevice, 
                                  &amp;m_InterruptReadRequest
                                  );

    if (SUCCEEDED(hr))
    {
        m_InterruptPipe-&gt;GetTargetFile(&amp;pTargetFile);
        hr = m_InterruptPipe-&gt;FormatRequestForRead(
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
        hr = m_InterruptReadRequest-&gt;Send(m_InterruptPipe, 0, 0);
    }

    return hr;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559230">IWDFIoTarget::FormatRequestForIoctl</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::CreateRequest method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

