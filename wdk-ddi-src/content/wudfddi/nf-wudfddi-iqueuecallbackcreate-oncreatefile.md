---
UID: NF:wudfddi.IQueueCallbackCreate.OnCreateFile
title: IQueueCallbackCreate::OnCreateFile (wudfddi.h)
description: The OnCreateFile method is called to handle an open file request when an application opens a device through the Microsoft Win32 CreateFile function.
old-location: wdf\iqueuecallbackcreate_oncreatefile.htm
tech.root: wdf
ms.date: 08/17/2022
keywords: ["IQueueCallbackCreate::OnCreateFile"]
ms.keywords: IQueueCallbackCreate interface,OnCreateFile method, IQueueCallbackCreate.OnCreateFile, IQueueCallbackCreate::OnCreateFile, OnCreateFile, OnCreateFile method, OnCreateFile method,IQueueCallbackCreate interface, UMDFQueueObjectRef_db0b57a0-6086-4e2a-87bd-71e5a1e4f46d.xml, umdf.iqueuecallbackcreate_oncreatefile, wdf.iqueuecallbackcreate_oncreatefile, wudfddi/IQueueCallbackCreate::OnCreateFile
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IQueueCallbackCreate::OnCreateFile
 - wudfddi/IQueueCallbackCreate::OnCreateFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IQueueCallbackCreate::OnCreateFile
---

# IQueueCallbackCreate::OnCreateFile

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **OnCreateFile** method is called to handle an open file request when an application opens a device through the Microsoft Win32 **CreateFile** function.

## -parameters

### -param pWdfQueue [in]

A pointer to the [IWDFIoQueue](./nn-wudfddi-iwdfioqueue.md) interface for the I/O queue object form which the request arrives.

### -param pWDFRequest [in]

A pointer to the [IWDFIoRequest](nn-wudfddi-iwdfiorequest.md) interface for the I/O request object for the device.

### -param pWdfFileObject [in]

A pointer to the [IWDFFile](./nn-wudfddi-iwdffile.md) interface for the file object that is associated with the device. This information is provided for convenience because the driver can call the [IWDFIoRequest::GetCreateParameters](./nf-wudfddi-iwdfiorequest-getcreateparameters.md) method to obtain the file object.

## -remarks

If the driver implements the [IQueueCallbackCreate](./nn-wudfddi-iqueuecallbackcreate.md) interface, the framework calls the **OnCreateFile** method when an application opens a device through the Win32 **CreateFile** function to perform an I/O operation, such as reading from or writing to a file. 

A driver registers the [IQueueCallbackCreate](./nn-wudfddi-iqueuecallbackcreate.md) interface when the driver calls the [IWDFDevice::CreateIoQueue](./nf-wudfddi-iwdfdevice-createioqueue.md) method to create an I/O queue or to configure the default I/O queue.

A typical **OnCreateFile** method might call [IWDFObject::AssignContext](./nf-wudfddi-iwdfobject-assigncontext.md) method on the file object to associate context with the file object, and then call [IWDFIoRequest::Complete](./nf-wudfddi-iwdfiorequest-complete.md) to complete the request.

A UMDF driver might be required to open registry keys or files while it impersonates a client that sends the I/O requests. From its implementation of the **OnCreateFile** method, the driver calls the [IWDFIoRequest::Impersonate](./nf-wudfddi-iwdfiorequest-impersonate.md) method to set a security impersonation level and to set the [IImpersonateCallback::OnImpersonate](./nf-wudfddi-iimpersonatecallback-onimpersonate.md) method in which the driver handles the impersonation. To access necessary resources by using the credentials of the user, the framework calls the driver's **OnImpersonate** method. For any operations other than those that require impersonation, the framework calls driver methods that run under the default driver account. For more information about how UMDF and UMDF drivers handle impersonation, see [Handling Impersonation](/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers).

### Examples

This example is based on the WpdWudfSampleDriver sample, and is from the Queue.cpp file.

```cpp
STDMETHODIMP_ (void) CQueue::OnCreateFile(
/*[in]*/ IWDFIoQueue* pQueue,
/*[in]*/ IWDFIoRequest* pRequest,
/*[in]*/ IWDFFile* pFileObject
)
{
  HRESULT hr = S_OK;
  ClientContext* pClientContext = new ClientContext ();

  // . . . Code omitted.

  if(pClientContext != NULL) {
    hr = pFileObject->AssignContext (this, (void*)pClientContext);

    // Release the client context if we cannot set it

    if(FAILED(hr)) {
      pClientContext->Release();
      pClientContext = NULL;
    }
  }
  else {
    hr = E_OUTOFMEMORY;
  }

  pRequest->Complete(hr);
}
```

## -see-also

- [IImpersonateCallback::OnImpersonate](./nf-wudfddi-iimpersonatecallback-onimpersonate.md)
- [IQueueCallbackCreate](./nn-wudfddi-iqueuecallbackcreate.md)
- [IWDFDevice::CreateIoQueue](./nf-wudfddi-iwdfdevice-createioqueue.md)
- [IWDFFile](./nn-wudfddi-iwdffile.md)
- [IWDFIoQueue](./nn-wudfddi-iwdfioqueue.md)
- [IWDFIoRequest](./nn-wudfddi-iwdfiorequest.md)
- [IWDFIoRequest::GetCreateParameters](./nf-wudfddi-iwdfiorequest-getcreateparameters.md)
- [IWDFIoRequest::Impersonate](./nf-wudfddi-iwdfiorequest-impersonate.md)
